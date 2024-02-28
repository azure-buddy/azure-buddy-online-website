---
title: "How to create an AKS Cluster using OpenTofu"
date: 2023-08-14
draft: false
description: "Short example how to create an AKS Cluster using OpenTofu."
slug: "create-aks-opentofu"
tags: ["tips", "tricks", "AKS", "OpenTofu", "Introduction", "IaC", "AVM", "VerifiedModules" ]
authors:
  - "avwsolutions"
---

# Introduction to the OpenTofu project part of the Linux Foundation

OpenTofu, previously known as OpenTF is a fork of Terraform that is truly open-source, community-driven, and managed by the Linux Foundation as sandbox project. More information about OpenTofu can be found at [OpenTofu.org](https://opentofu.org/).

{{< alert >}}
Make sure you are using **OpenTofu version 1.61.1** or later to take advantage of some of the latest OpenTofu features.
{{< /alert >}}


# Migrating to OpenTofu from Terraform

Since OpenTofu (1.6) release is compatible with Terraform 1.6 release you currently will not expect big issues, but over time this can change when new features are introduced. This blog is about applying [Microsoft Learn Terraform Quickstarts](https://learn.microsoft.com/en-us/azure/developer/terraform/) with OpenTofu and actually experience the compatbility. You may also want to have a look at [Azure Verified Modules](https://azure.github.io/Azure-Verified-Modules/), which are available for Terraform.

This first series we are going to look at the Quickstart how to deploy an Azure Kubernetes Service (AKS) cluster using OpenTofu instead of Terraform. 

What can be expect? Do thing break or wil everything work as expected?

As refresher we wil dive into the OpenTofu basics first.

{{< alert >}}
Important action is noted at [Step zero](https://opentofu.org/docs/intro/migration/) by always preparing a disaster recovery plan. Wrongly Infrastructure-as-Code parameters can wrongly configure or even destroy live Production environments.
{{< /alert >}}

# Install OpenTofu on Windows

OpenTofu CLI supports all popular operating systems like Windows. Installing OpenTofu CLI on Windows is easy and can be done using PowerShell standalone installer.

Optionally you can verify the file integrity using checksum validation. Read more about this on [OpenTofu: Standalone Installation](https://opentofu.org/docs/intro/install/standalone/).

```PowerShell
# Let's grep the latest installer script:
Invoke-WebRequest -outfile "install-opentofu.ps1" -uri "https://get.opentofu.org/install-opentofu.ps1"

# Run the installer using the standalone method:
& .\install-opentofu.ps1 -installMethod standalone

# Don't forget to cleanup the installer:
Remove-Item install-opentofu.ps1
```

# Hello World example using OpenTofu

## Creating new Azure Resource Group

This `Hello World` example you wil learn the basics of OpenTofu by creating an Azure Resource Group. You wil start with writing down the code, which is actually called `OpenTofu language`. You may recognize the same syntax when writing `Hashicorp Configuration Language` code. This example uses the `azurerm` provider is actually copied to the `OpenTofu` registry from the `HashiCorp` registry.

```
provider "azurerm" {
  skip_provider_registration = true
  features {}
}

resource "azurerm_resource_group" "Hello_World" {
  name     = "My-Resource-Group-01"
  location = "South Central US"
}
```

Above the most simplest way to create a Azure Resource Group called `My-Resource-Group-01` at location `South Central US` using OpenTofu. You may have to login to authenticate the `provider` against Azure using the CLI.

```
az login --scope https://graph.microsoft.com/.default
```

First let's `init` the configuration. This will download the provider from the `OpenTofu` registry to a local directory `.terraform` and a lock file called `.terraform.lock.hcl` is created.

```
tofu init
```

Everything still green? That's great. Let's continue with the plan phase. In our case the Azure Resource Group doesn't exist, so we expect a creation result. 

```
tofu plan
```

Example output you can expect.
```
OpenTofu used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create

OpenTofu will perform the following actions:

  # azurerm_resource_group.Hello_World will be created
  + resource "azurerm_resource_group" "Hello_World" {
      + id       = (known after apply)
      + location = "southcentralus"
      + name     = "My-Resource-Group-01"
    }

Plan: 1 to add, 0 to change, 0 to destroy.

─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Note: You didn't use the -out option to save this plan, so OpenTofu can't guarantee to take exactly these actions if you run "tofu apply" now.
```

Awesome. You are now ready to create your first resource using OpenTofu. Also notice that `plan` is only a dry-run and no resources or local cache is created. You may want to save the plan for future use using the `-out` flag.

```
tofu apply
```

Apply by default asks for approval performing the actions. Just answer with yes or use the `-auto-approve` flag for dare devils!
After running `apply` you wil find an new file created called `terraform.tfstate`. This file contains the current configuration state and can contain confidential data, so ensure proper permissions are set.

Using the `tofu` CLI you can also `list` the stored resource objects in the `tfstate` file. Since you have successfully applied the configuration you wil see 
`azurerm_resource_group.Hello_World` resource. You can even `show` the actual resource configuration.

```
tofu state list
azurerm_resource_group.Hello_World

tofu state show azurerm_resource_group.Hello_World
# azurerm_resource_group.Hello_World:
resource "azurerm_resource_group" "Hello_World" {
    id       = "/subscriptions/xxxxxxx-afca-yyyy-zzzz-000000000000/resourceGroups/My-Resource-Group-01"
    location = "southcentralus"
    name     = "My-Resource-Group-01"
    tags     = {}
}

```

Let's dive into another use case when your Azure Resource Group already exists!

## Importing existing Azure Resource Group

You have learned how to create a new Azure Resource Group, but what if you already have an existing Azure Resource Group? No problem at all!
This situation we can use `import` to add the resource to our `tfstate`.

Important to remember is that `tofu import` requires an Id, which is not the name you may set in your `main.tf` file. Instead this contains the unique `Subscription Id path`, like is shown in the `state` configuration.

let's find the Id first using the `az CLI`. Group list will show JSON parsed output, which will include the actual Id.

```
az group list
```

Expected output:
```
[
  {
    "id": "/subscriptions/xxxxxxx-afca-yyyy-zzzz-000000000000/resourceGroups/My-Resource-Group-02",
    "location": "southcentralus",
    "managedBy": null,
    "name": "My-Resource-Group-02",
    "properties": {
      "provisioningState": "Succeeded"
    },
    "tags": null,
    "type": "Microsoft.Resources/resourceGroups"
  }
]

```

In our case we have created this new group with the az CLI. Example `az group create --location southcentralus --resource-group My-Resource-Group-02`

Now start updating the `main.tf` configuration to reflect this group.

```
provider "azurerm" {
  skip_provider_registration = true
  features {}
}

resource "azurerm_resource_group" "Hello_World" {
  name     = "My-Resource-Group-02"
  location = "South Central US"
}
```
To build up the parameters we need the `Resource Type`, `Resource Name` and mentioned Id.

```
tofu import azurerm_resource_group.Hello_World /subscriptions/xxxxxxx-afca-yyyy-zzzz-000000000000/resourceGroups/My-Resource-Group-02
```

After running this import you may see the imported resource in your `state listing` using `tofu state list`.

# Walkthrough Microsoft Quickstart deploying an Azure Kubernetes Service (AKS) cluster using OpenTofu

This walkthrough is created to guide you through the [Quickstart Kubernetes deployment](https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-terraform?tabs=bash). Instead of Terraform we will use OpenTofu.

First thing is to clone the [Azure Terraform](https://github.com/Azure/terraform.git) repository. For convinience we added this repository as Git submodule to our blog content.

The quickstart provides five (5) Terraform configuration files. 

## Analyse current  Terraform configuration code

First we are going to analyse the current configuration code. 
- Are the providers and module available in OpenTofu?
- Are their any dedicated version limitations (like before Terraform 1.6) ?

For this analysis you may want to take a look at the [OpenTofu Registry](https://opentofu.org/registry/).

## Inspect provider initialization

Ensure that you are in the working directory where the Terrfaform configuration files are located. 

Now initialize tofu.

```
tofu init -upgrade
```

When everything goes well you have an exspected output like below:
```
Initializing the backend...

Initializing provider plugins...
- Finding hashicorp/random versions matching "~> 3.0"...
- Finding hashicorp/time versions matching "0.9.1"...
- Finding azure/azapi versions matching "~> 1.5"...
- Finding hashicorp/azurerm versions matching "~> 3.0"...
- Installing hashicorp/random v3.6.0...
- Installed hashicorp/random v3.6.0 (signed, key ID 0C0AF313E5FD9F80)
- Installing hashicorp/time v0.9.1...
- Installed hashicorp/time v0.9.1 (signed, key ID 0C0AF313E5FD9F80)
- Installing azure/azapi v1.12.0...
- Installed azure/azapi v1.12.0. Signature validation was skipped due to the registry not containing GPG keys for this provider
- Installing hashicorp/azurerm v3.91.0...
- Installed hashicorp/azurerm v3.91.0 (signed, key ID 0C0AF313E5FD9F80)

Providers are signed by their developers.
If you'd like to know more about provider signing, you can read about it here:
https://opentofu.org/docs/cli/plugins/signing/

OpenTofu has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that OpenTofu can guarantee to make the same selections by default when
you run "tofu init" in the future.

OpenTofu has been successfully initialized!

You may now begin working with OpenTofu. Try running "tofu plan" to see
any changes that are required for your infrastructure. All OpenTofu commands
should now work.

If you ever set or change modules or backend configuration for OpenTofu,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```

Everything looks great and ensure that the `.terraform` and `.terraform.lock.hcl` are created.

## Plan your configuration to apply

You are now ready to create a plan file. As mentioned in the previous chapter we can store the expected activities to a plan file.

```
tofu plan -out main.tfplan 
```

After a succesfull plan phase a `main.tfplan` file is created. Take a look into this file with `tofu show main.tfplan` and notice that five (5) resource blocks are added.

## Apply the configuration and create all required resources

Now you may want to apply the configuration and create all resources in Azure that you have stored in the `main.tfplan`.

```
tofu apply main.tfplan
```

# Conclusion

Most scenario's you can easily migrate existing Terraform code with minor adjustments towards OpenTofu. Import to keep in mind is that over time products will differentiate and tool specific features are introduced. We can't look into the future, but for now OpenTofu is a drop-in replacement for Terraform and compatible with 1.5.x and 1.6.x releases.

Hopefully you liked this Tip & tricks introduction into the OpenTofu project article and how to reuse Microsoft Learn Quickstart material to create an AKS Cluster using OpenTofu.

# Interested in the code?

All code samples, including a link to the Azure sample repository is available at [Azure Buddy Github](https://github.com/azure-buddy/howto-create-aks-opentofu-example).

Contributions or follow-up articles are more than appreciated!