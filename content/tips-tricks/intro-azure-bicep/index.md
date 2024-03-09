---
title: "Introduction to Azure Bicep"
date: 2024-03-09
draft: false
description: "Short introduction how to use and develop with Azure Bicep."
slug: "intro-azure-bicep"
tags: ["tips", "tricks", "Azure", "ARM", "Bicep", "Introduction", "IaC", "AVM", "VerifiedModules" ]
authors:
  - "avwsolutions"
---

# Introduction to Bicep

If you are familiar with Azure Cloud you may have heard of Bicep.Bicep is a domain-specific language (DSL) that simplifies the authoring and management of Azure Resource Manager (ARM) templates. Bicep tries to solve challenges that affect the development lifecycle, rather complex JSON files by introducing a friendly syntax that provides a delarative structure to define `params` and `resources` with less coding.

Main goals are developer friendly and faster results by enabling:
- Concise syntax
- Code reuse
- Resource consistency

{{< alert >}}
Want to learn more about Bicep? the following Microsoft Learn documentation on [Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/)
{{< /alert >}}

# Compare with other IaC tools

Just like other IaC tools we have most expected features available, such as providing 'idempotent' deployments. In short:

- Deploy with confidence in a repeatable matter. You define the *Desired State* in Bicep files.
- Orchestration becoming easier and doesn't require multiple imperative tasks since dependencies and ordering are managed by the Azure Resource Manager.
- New supported resources are easily provided by *Modules*. You can even create your own modules!
- You can use the *What If* operation to preview changes, before applying the actual deployment.

# Benefits of using Bicep as platform foundation language

Bicep does have various benefits when looking at ARM templates or using other IaC languages. This is especially the case when you are deploying Azure platform services. Great advantage is that support for new Azure resource types and API versions are directly available with GA releases, which saves time and potential integration hassle. additionally all state is automatically stored in Azure, so you don't have to set up and maintain additional resources.

# Effectively work with Bicep as IaC language

Below are some `tips and tricks` for effectively working with this Infrastructure-as-Code (IaC) language.




# Interested in the code?

All code samples, including a link to the Azure sample repository is available at [Azure Buddy Github](https://github.com/azure-buddy/intro-azure-bicep).

Contributions or follow-up articles are more than appreciated!