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

Just like other IaC tools we have most expected features available, such as providing *idempotent deployments*. In short:

- Deploy with confidence in a repeatable matter. You define the *Desired State* in Bicep files.
- Orchestration becoming easier and doesn't require multiple imperative tasks since *dependencies and ordering are managed* by the Azure Resource Manager.
- New supported resources are easily provided by *Modules*. You can even create your own modules!
- You can use the *What If* operation to preview changes, before applying the actual deployment.

# Benefits of using Bicep as platform foundation language

Bicep does have various benefits when looking at ARM templates or using other IaC languages. This is especially the case when you are deploying Azure platform services. Great advantage is that support for new Azure resource types and API versions are directly available with GA releases, which saves time and potential integration hassle. additionally all state is automatically stored in Azure, so you don't have to set up and maintain additional resources.

Some good practices to explore are provided through Azure Verfified Modules (AVM), but more specific to the Cloud Adoption Framework (CAF) you can reuse the  newest Azure Subscription Vending modules combined with the generic Azure Landing Zone (ALZ) modules.

:point_right: [Generic ALZ Modules](https://github.com/Azure/ALZ-Bicep)

:point_right: [Newest Subscription Vending Modules](https://github.com/Azure/bicep-lz-vending)

# Effectively work with Bicep as IaC language

Below are some `tips and tricks` for effectively working with this Infrastructure-as-Code (IaC) language.

- Understand the foundational knowledge of working with Azure Resource Manager (ARM). Bicep is essentially a more concise and readable way to write ARM templates, but understanding how ARM works is crucial for smooth development.

 :point_right: [ARM Overview](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/overview)

- Improve your development experience by using the VSCode Bicep extension. Bicep extension provides features like syntax highlighting, snippets, intellisense/completions and more.

:point_right: [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-bicep)

- Leverage the Bicep CLI. The Bicep CLI offers commands for building, validating, and decompiling Bicep files. Familiarize yourself with these commands to streamline your development workflow.

:point_right: [Bicep CLI Reference](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/bicep-cli)

- Foster a good developer mindset, think like a programmer, follow common DevOps patterns and practices like reuse code with modules. Bicep supports modules, which allow you to break down your code into smaller, reusable code blocks. This can make your templates more modular and easier to maintain.

:point_right: [DevOps Patterns & Practices](https://learn.microsoft.com/en-us/devops/what-is-devops)

# Interested in the code?

All code samples, including a link to the Azure sample repository is available at [Azure Buddy Github](https://github.com/azure-buddy/intro-azure-bicep).

Contributions or follow-up articles are more than appreciated!