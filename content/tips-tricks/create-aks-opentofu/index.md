---
title: "How to create an AKS Cluster using OpenTofu"
date: 2020-08-14
draft: false
description: "Short example how to create an AKS Cluster using OpenTofu."
slug: "create-aks-opentofu"
tags: ["tips", "tricks", "AKS", "OpenTofu" ]
series: ["Tips & Tricks"]
series_order: 4
---

# How to create an AKS Cluster using OpenTofu

OpenTofu, previously known as OpenTF is a fork of Terraform that is truly open-source, community-driven, and managed by the Linux Foundation as sandbox project. More information about OpenTofu can be found at [OpenTofu.org](https://opentofu.org/).

{{< alert >}}
Make sure you are using **OpenTofu version 1.61.1** or later to take advantage of some of the latest OpenTofu features.
{{< /alert >}}

If you are familiar with Terraform, common scenario to keep things simple is to start with three configuration files

```shell
provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "Azure_RG" {
  for_each = var.resource_groups
  name     = each.key
  location = each.value.location
}

resource "azurerm_kubernetes_cluster" "AKS_Cluster" {
  for_each            = var.kube_params
  name                = each.key
  location            = azurerm_resource_group.this[each.value.rg_name].location
  resource_group_name = azurerm_resource_group.this[each.value.rg_name].name
  dns_prefix          = each.value.dns_prefix

  default_node_pool {
    enable_auto_scaling = each.value.enable_auto_scaling
    max_count           = each.value.enable_auto_scaling ? each.value.max_count : null
    min_count           = each.value.enable_auto_scaling ? each.value.min_count : null
    node_count          = each.value.node_count
    vm_size             = each.value.vm_size
    name                = each.value.np_name
  }

  dynamic "service_principal" {
    for_each = each.value.service_principal
    content {
      client_id     = service_principal.value.client_id
      client_secret = service_principal.value.client_secret
    }
  }

  dynamic "identity" {
    for_each = each.value.identity
    content {
      type         = identity.value.type
      identity_ids = identity.value.identity_ids
    }
  }
  tags = each.value.tags
}
```

```shell
output "Azure_RG" {
  description = "Output handler for Azure Resource Groups"
  value       = { for rg in azurerm_resource_group.Azure_RG : rg.name => rg.location }
}

output "AKS_Cluster" {
  description = "Output handler for Azure Kubernetes Service cluster"
  value       = { for cluster in azurerm_kubernetes_cluster.AKS_Cluster : cluster.name => { "id" : cluster.id, "fqdn" : cluster.fqdn } }
}
```

```shell
variable "resource_groups" {
  description = "Resource Groups Parameters"
  type = map(object({
    location = string
  }))
  default = {
    rg1 = {
      location = "westeurope"
    }
  }
}

variable "aks_params" {
  description = "AKS parameters"
  type = map(object({
    rg_name             = string
    dns_prefix          = string
    np_name             = string
    tags                = optional(map(string), {})
    vm_size             = optional(string, "Standard_B2s")
    client_id           = optional(string, null)
    client_secret       = optional(string, null)
    enable_auto_scaling = optional(bool, false)
    max_count           = optional(number, 1)
    min_count           = optional(number, 1)
    node_count          = optional(number, 1)
    service_principal = optional(list(object({
      client_id     = string
      client_secret = string
    })), [])
    identity = optional(list(object({
      type         = optional(string, "SystemAssigned")
      identity_ids = optional(list(string), [])
    })), [{}])
  }))
  default = {
    aks1 = {
      rg_name    = "rg1"
      dns_prefix = "k8s"
      np_name    = "np1"
    }
  }
}
```