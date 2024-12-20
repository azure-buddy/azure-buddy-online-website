---
title: "Azure Buddy Monthly recap: July 2024"
date: 2024-07-02
draft: false
description: "Monthly recap of Azure updates."
slug: "update-jul-2024"
tags: ["blogs", "azure", "updates", "monthly", "security", "containers", "management"]
series: ["Monthly recap of Azure updates"]
series_order: 7
---

# Monthly recap of Azure updates 

An easy-to-scan roundup of our newest, most important highlights. Let's have a look what interested Azure updates are share. Read carefully through the updates, especially the products and support that are announced as becoming `retired`.

This month a lot of things went `Generally Available`, next to `retired` services like the *Microsoft.AlertsManagement.Alerts* API.

Most important two around `Security` / `Sovereign Engineering` are the possibility of using `Customer Managed Keys` for encryption in **Backup Vaults** and the support of `Azure Trusted Launch VMs` in **Azure Site Recovery** is starting with Windows VMs.

## Top 5 you don't want to miss

1. Advanced network `Observability` in **AKS** using `Cilium` or `Retina`. Retina delivers `Windows Node Support`. Looking for an brief introduction?, read my latest blog called [Introduction into Retina Network Observability for Kubernetes](https://azurebuddy.online/tips-tricks/intro-retina-obs/).
2. When working with `Kusto` databases using tools like **Azure Data Explorer**, the recently added command to `.update` records became GA. Really helpful for `ingestion use cases`.
3. Take a moment to inform your procurement department. Microsoft is discontinuing the EA and MCA-E Support Plan Promotional Offer on 30 June 2024. New alternative Support plans are available. Additonal some new capabilities are added to the `Azure Monitor Basics Log Plan`.
4. Some improvement features are now available for **ExpressRoute** like `FastPath` integration support with VNets and UDR and `Traffic Collector` support for provider circuits. `FastPath` helps to increase performance and throughput.
5. Deleting or resetting **Azure Site Recovery** appliances is now available. A long waiting feature.

Look at the comprehensive list below for more information.

## Azure updates

- [Public Preview: Convert to Azure Premium SSD v2 disks](https://azure.microsoft.com/en-us/updates/v2/convert-to-azure-premium-ssd-v2)
- [Public Preview: New Azure Monitor Auxiliary Logs Plan](https://azure.microsoft.com/en-us/updates/v2/Azure-Monitor-Auxiliary-Logs)
- [Public Preview: Azure NetApp Files large volume enhancement – increased throughput and maximum size limit of 2 PiB volume](https://azure.microsoft.com/en-us/updates/v2/Large-Volume-enhancements)
- [Public Preview: 6th generation Intel-based VMs – Dv6/Ev6](https://azure.microsoft.com/en-us/updates/v2/6th-generation-Intel-based-VMs-Dv6-Ev6)
- [Generally Available: New capabilities added to Azure Monitor Basic Logs plan](https://azure.microsoft.com/en-us/updates/v2/Azure-Monitor-Basic-Logs-Updates)
- [Generally Available: AzAcSnap 10 — Azure Application Consistent Snapshot tool updates](https://azure.microsoft.com/en-us/updates/v2/AzAcSnap-10-GA)
- [Generally Available: Delete or Reset Azure Site Recovery replication appliance](https://azure.microsoft.com/en-us/updates/v2/azure-site-recovery-delete-reset-appliance-announcement)
- [Retirement: App Service Environment v1/v2 will be retired on August 31, 2024](https://azure.microsoft.com/en-us/updates/v2/App-Service-Environment-Retirement-Update)
- [Retirement: Azure Lab Services is being retired on June 28, 2027](https://azure.microsoft.com/en-us/updates/v2/Azure-Lab-Services-is-being-retired)
- [Public Preview: Upgrade existing Azure Gen1/Gen2 VMSS to Gen2-Trusted launch](https://azure.microsoft.com/en-us/updates/v2/public-preview-upgrade-existing-vmss-to-trusted-launch)
- [Retirement: Azure Synapse Runtime for Apache Spark 3.2](https://azure.microsoft.com/en-us/updates/v2/azure-synapse-runtime-for-apache-spark-32-deprecated)
- [Retirement: Azure Synapse Runtime for Apache Spark 3.3](https://azure.microsoft.com/en-us/updates/v2/Azure-Synapse-runtime-Apache-Spark-3-3-EOS)
- [Generally Available: Support for .NET 8 using the in-process model in Azure Functions](https://azure.microsoft.com/en-us/updates/v2/Azure-Functions-supports-NET8-using-in-process-model)
- [Generally Available: Redis extension for Azure Functions](https://azure.microsoft.com/en-us/updates/v2/Redis-Extension-Azure-Functions)
- [Public Preview: Managed Java component (Admin for Spring) in Azure Container Apps](https://azure.microsoft.com/en-us/updates/v2/Preview-Managed-Java-component-in-Azure-Container-Apps)
- [Public Preview: Managed identity support for scaling rules in Azure Container Apps](https://azure.microsoft.com/en-us/updates/v2/Preview-Managed-identity-support-for-scaling-rules-ACA)
- [Generally Available: Azure Container Apps support for peer-to-peer encryption](https://azure.microsoft.com/en-us/updates/v2/GA-ACA-support-for-peer-to-peer-encryption)
- [Generally Available: Support for Azure Key Vault certificates in Azure Container Apps](https://azure.microsoft.com/en-us/updates/v2/Support-for-Azure-Key-Vault-certificates-ACA)
- [Generally Available: ExpressRoute Traffic Collector support for provider circuits](https://azure.microsoft.com/en-us/updates/v2/ExpressRoute-Traffic-Collector-Support-For-Provider-Circuits)
- [Generally Available: ExpressRoute FastPath Support for Vnet Peering & UDR](https://azure.microsoft.com/en-us/updates/v2/ExpressRoute-FastPath-Support)
- [Generally Available: Azure Virtual Network Manager mesh and direct connectivity](https://azure.microsoft.com/en-us/updates/v2/Azure-Virtual-Network-Manager-Mesh-direct-connectivity)
- [Public Preview: Azure Data Box now supports select cross region transfers](https://azure.microsoft.com/en-us/updates/v2/cross-region-transfers-for-azure-data-box)
- [Retirement: API “Microsoft.AlertsManagement alerts 2018-05-05-preview”](https://azure.microsoft.com/en-us/updates/v2/Alerts-Management-Alerts-Deprectaion)
- [General Availability: Pgvector 0.7 support in Azure Database for PostgreSQL – Flexible Server](https://azure.microsoft.com/en-us/updates/v2/Pgvector-support-in-Azure-Database)
- [General Availability: Major version upgrade support for PostgreSQL 16](https://azure.microsoft.com/en-us/updates/v2/Major-version-upgrade-support-for-PostgreSQL16)
- [General Availability: Latest PostgreSQL minor versions supported by Azure Database for PostgreSQL - Flexible Server](https://azure.microsoft.com/en-us/updates/v2/Latest-PostgreSQL-minor-versions-supported)
- [General Availability: Multi-select delete in Azure Cosmos DB with Data Explorer](https://azure.microsoft.com/en-us/updates/v2/GA-Multi-select-delete-Cosmos-DB)
- [Generally Available: Update records in a Kusto Database](https://azure.microsoft.com/en-us/updates/v2/Update-Records-in-Kutso-Databases)
- [Azure Cloud Services Guest OS Families 2, 3, and 4 Retirement](https://azure.microsoft.com/en-us/updates/v2/Guest-OS-Family-Retirement)
- [Generally Available: Encryption using Customer Managed Keys for Backup Vaults](https://azure.microsoft.com/en-us/updates/v2/cmk-for-backup-vaults-ga/)
- [Generally Available: Backup and restore of virtual machines with private endpoint enabled disks](https://azure.microsoft.com/en-us/updates/v2/azure-backup-vm-disk-access-ga)
- [Generally Available: Azure Elastic SAN Feature Updates](https://azure.microsoft.com/en-us/updates/v2/Azure-Elastic-SAN-Feature-Updates)
- [Public Preview: Advanced Network Observability for your Azure Kubernetes Service clusters through Azure Monitor](https://azure.microsoft.com/en-us/updates/v2/Advanced-Network-Observability-AKS)
- [Generally Available: Azure Site Recovery support for Azure Trusted Launch VMs (Windows OS)](https://azure.microsoft.com/en-us/updates/v2/generally-available-azure-site-recovery-support-for-azure-trusted-launch-vms-windows-os)
- [Generally Available: Run your Databricks Jobs with Serverless compute for workflows](https://azure.microsoft.com/en-us/updates/v2/Databricks-Jobs-Serverless-Compute)
- [Generally Available: Interactive Serverless Compute](https://azure.microsoft.com/en-us/updates/v2/interactive-serverless-compute-AU)
- [Generally Available: DLT with serverless compute](https://azure.microsoft.com/en-us/updates/v2/DLT-Serverless-Compute)
- [Public preview: Cisco Firepower Threat Defense (FTD) integration with Virtual WAN](https://azure.microsoft.com/en-us/updates/v2/Cisco-Firepower-Threat-Defense)
- [Public Preview: Azure CDN Standard From Microsoft (classic) zero-downtime migration to Azure Front Door](https://azure.microsoft.com/en-us/updates/v2/CDN-Standard-Form-Azure-Front-Door)
- [In development: ExpressRoute Resiliency Enhancements](https://azure.microsoft.com/en-us/updates/v2/ExpressRoute-Resiliency-Enhancements)
- [Public Preview: Online Migration for MongoDB in Azure Data Studio](https://azure.microsoft.com/en-us/updates/v2/Online-Migration-MongoDB-Azure-Data-Studio)
- [Public Preview: Azure SQL updates for early-July 2024](https://azure.microsoft.com/en-us/updates/v2/Preview-Azure-SQL-July-2024)
- [Public preview: Azure cross-subscription Load Balancer](https://azure.microsoft.com/en-us/updates/v2/Cross-Subscription-Load-Balancer)
- [Private Preview: Azure Backup for Elastic SAN](https://azure.microsoft.com/en-us/updates/v2/Azure-Backup-for-Elastic-SAN)
- [Retirement: Onco-Phenotype model within Azure AI Health Insights](https://azure.microsoft.com/en-us/updates/v2/OncoPhenotype-with-Azure-Health-Insights-Retirement)
- [Public Preview: Azure Machine Learning Announcement](https://azure.microsoft.com/en-us/updates/v2/Azure-Machine-Learning-Announcements-Preview)
- [Generally Available: Azure Machine Learning Announcement](https://azure.microsoft.com/en-us/updates/v2/Azure-Machine-Learning-GA)
- [Generally Availabile: Spain Central region added to Azure HDInsight](https://azure.microsoft.com/en-us/updates/v2/Spain-Central-added-to-Azure-HDInsight)
- [Generally Available: Azure Log Alerts support for Azure Data Explorer](https://azure.microsoft.com/en-us/updates/v2/Log-Alerts-for-Azure-Data-Explorer)
- [Public Preview: Force detach zone redundant data disks during zone outage](https://azure.microsoft.com/en-us/updates/v2/Force-Detach-Zone)
- [Public Preview: ED25519 SSH key support for Linux virtual machines](https://azure.microsoft.com/en-us/updates/v2/SSH-Key-Support-for-Linux-VMs)
- [Public Preview: Continuous Performance Diagnostics for Windows VMs to enhance VM Troubleshooting](https://azure.microsoft.com/en-us/updates/v2/Continuous-Performance-Diagnostics-for-Windows-VMSs)
- [Windows Server 2025 now available for public preview](https://azure.microsoft.com/en-us/updates/v2/Windows-Server-2025-Preview)
- [404 - Not Found](https://azure.microsoft.com/en-us/updates/v2/Redis-7.2-on-Azure-Cache)
- [Online migration in migration service Azure Database for PostgreSQL](https://azure.microsoft.com/en-us/updates/v2/Migration-Service-Azure-DB-PostgreSQL)
- [Extension version sync for Azure Database for PostgreSQL - Flexible Server](https://azure.microsoft.com/en-us/updates/v2/Extension-version-sync-Azure-DB-PostgreSQL)
- [New Azure Advisor recommendations for Azure Database for PostgreSQL - Flexible Server](https://azure.microsoft.com/en-us/updates/v2/Advisor-Recommendation-Azure-DB-PostgreSQL)
- [IOPS scaling for Azure Database for PostgreSQL - Flexible Server](https://azure.microsoft.com/en-us/updates/v2/IOPS-for-Azure-DB-for-PostgreSQL)
- [Generally Available: Azure SQL updates for late-June 2024](https://azure.microsoft.com/en-us/updates/v2/SQL-Updates-June-2024)
- [Public Preview: Geo-Replication for Azure Service Bus Premium](https://azure.microsoft.com/en-us/updates/v2/Geo-Replication-Service-Bus-Premium)
- [Public Preview: JavaScript (JS) Challenge on Azure WAF integrated with Azure Application Gateway](https://azure.microsoft.com/en-us/updates/v2/Javascript-Challenge-on-Azure-WAF)
- [Public Preview: Azure Container Apps available in Azure Government Cloud Virginia](https://azure.microsoft.com/en-us/updates/v2/Container-Apps-in-Azure-Government-Cloud)
- [Generally Available: Announcing kube-egress-gateway for Kubernetes](https://azure.microsoft.com/en-us/updates/v2/kube-egress-gateway-for-Kubernetes)
- [Generally Available: OS Security Patch channel for Linux in AKS](https://azure.microsoft.com/en-us/updates/v2/OS-Security-Patch-Channel-For-Linux)
- [Generally Available: az command invoke in AKS](https://azure.microsoft.com/en-us/updates/v2/az-command-invoke-in-AKS)
- [Public Preview: Upgrade Policies for Virtual Machine Scale Sets with Flexible Orchestration](https://azure.microsoft.com/en-us/updates/v2/VM-Scale-Sets-Flexible-Orchestration)
- [Generally Available: Azure Monitor Log Enablement Policy Expansion](https://azure.microsoft.com/en-us/updates/v2/Log-Enablement-Policy-Expansion)
- [Generally Available: Azure Monitor OpenTelemetry-based Distro adds Live Metrics](https://azure.microsoft.com/en-us/updates/v2/Azure-Monitor-Distro-Metrics)
- [Generally Available: Azure Virtual Network Manager mesh and direct connectivity](https://azure.microsoft.com/en-us/updates/v2/GA-Virtual-Network-Manager-mesh-and-direct-connectivity)
- [Generally Available: Run load tests in debug mode on Azure Load Testing](https://azure.microsoft.com/en-us/updates/v2/Run-Load-Test-Debug-Mode)
- [Public Preview: Summary rules in Azure Monitor Log Analytics, for optimal consumption experiences and cost](https://azure.microsoft.com/en-us/updates/v2/Preview-Summary-Rules-Azure-Monitor-Log-Analytics)
- [Generally Available: Azure Monitor, Log Analytics dedicated clusters now supported in Azure portal](https://azure.microsoft.com/en-us/updates/v2/Azure-Monitor-Log-Analytics-Support)
- [Public Preview: Announcing Foundation Model Training](https://azure.microsoft.com/en-us/updates/v2/Foundation-Model-Training)
- [Generally Available: Run Azure Load Testing on Azure Functions](https://azure.microsoft.com/en-us/updates/v2/Azure-Load-Testing-Azure-Functions)
- [Azure support plan offer being discontinued on June 30, 2024](https://azure.microsoft.com/en-us/updates/v2/Azure-Support-Plan-Discontinued)
- [General Availability: vCore-based Azure Cosmos DB for MongoDB now supports Mongo Ver 7.0](https://azure.microsoft.com/en-us/updates/v2/vCore-Azure-Cosmos-DB-for-MongoDB-supports-v7)
- [Public Preview: Azure Cosmos DB continuous backup for accounts using Azure Synapse Link](https://azure.microsoft.com/en-us/updates/v2/Cosmos-DB-continuous-backup-Azure-Synapse-Link)
- [Public Preview: Azure SQL updates for mid-June 2024](https://azure.microsoft.com/en-us/updates/v2/Azure-SQL-Updates-June-2024)
