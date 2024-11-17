---
title: "Azure Buddy Monthly recap: October 2024"
date: 2024-10-02
draft: false
description: "Monthly recap of Azure updates."
slug: "update-oct-2024"
tags: ["blogs", "azure", "updates", "monthly", "security", "containers", "management"]
series: ["Monthly recap of Azure updates"]
series_order: 10
---

# Monthly recap of Azure updates 

An easy-to-scan roundup of our newest, most important highlights. Let's have a look what interested Azure updates are share. Read carefully through the updates, especially the products and support that are announced as becoming `retired`.

This month seems all about updates and features going `Generally Available`. `Retirement` has been announced for `Azure Spring Apps`, which can be important for Enterprise customers. No **AKS** and **Security** updates this month, but still enough to talk about.

## Top 5 you don't want to miss

1. It's time to replace your **Azure Diagnostic Extension for Windows and Linux (WAD/LAD)** by making use of the **Azure Monitoring Agent (AMA)**. Read the following page how to migrate the functionality to [Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/diagnostics-extension-overview).
2. Starting with FinOps, but still looking for some guiding documentation that includes best practices? Don't look further and dive into the FinOps Toolkit. Freely available to accelerate your FinOps journey here [FinOps Toolkit](https://microsoft.github.io/finops-toolkit/).
3. Having performance issues with **PostgreSQL Azure Databases**? Things get easier to troubleshoot and diagnose by setting performance management server parameters. Think about **parallel workers**, **temp file limit**, **enabling incremental sort** and more.
4. The **Azure Storage Account** default egress limit has been increased from 120 Gbps to 200 Gbps for both existing and new storage accounts.
5. In large environments it's crucial to do efficient **IP Address Management (IPAM)**. To simplify this a new feature is under `Public Preview` called **Azure Virtual Network IP address management**. It helps to plan and allocate both cloud, on-premise IPs and ensures there are no overlaps or misconfigurations and provides a clear overview of the **Azure Virtual Network Manager** managed resources.

Look at the comprehensive list below for more information.

## Azure updates

- [Retirement: Update on retirement of TLS 1.0 and TLS 1.1 versions for Azure Services](https://azure.microsoft.com/en-us/updates/v2/Update-retirement-TLS1-0-TLS1-1-versions-Azure-Services)
- [Generally Available: Azure App Configuration – Premium pricing plan now generally available](https://azure.microsoft.com/en-us/updates/v2/Azure-App-Configuration-Premium-pricing-plan-now-generally-available)
- [Public Preview: Azure Functions support for Node.js 22](https://azure.microsoft.com/en-us/updates/v2/Azure-Functions-support-for-Nodejs-22)
- [Generally Available: FinOps toolkit 0.6 - September 2024](https://azure.microsoft.com/en-us/updates/v2/FinOps-toolkit-0-6-September-2024)
- [Generally Available: Set fail criteria on server metrics in Azure Load Testing](https://azure.microsoft.com/en-us/updates/v2/fail-criteria-on-server-metrics-in-MALT)
- [Generally Available: In-place scaling for Enterprise caches](https://azure.microsoft.com/en-us/updates/v2/In-place-scaling-for-Enterprise-caches)
- [Generally Available: Azure SQL updates for late-October 2024](https://azure.microsoft.com/en-us/updates/v2/Azure-SQL-updates-for-late-October-2024)
- [Generally Available: ED25519 SSH key support for Linux VMs](https://azure.microsoft.com/en-us/updates/v2/linux-sssh-ed25519)
- [Generally Available: Azure Cobalt 100 Arm-based Virtual Machines](https://azure.microsoft.com/en-us/updates/v2/Azure-Cobalt-100-Arm-based-Virtual-Machines)
- [Public Preview: VM watch for Azure VMs](https://azure.microsoft.com/en-us/updates/v2/VM-watch-on-Azure-VMs)
- [Generally Available: Reduced Pricing for JBoss EAP on App Service](https://azure.microsoft.com/en-us/updates/v2/Reduced-Pricing-for-JBoss-EAP-on-App-Service)
- [Generally Available: ExpressRoute Metro](https://azure.microsoft.com/en-us/updates/v2/Ermetro-ga-announcement)
- [Generally Available: GRS and CRR support for Azure VMs using Premium SSD v2 and Ultra Disk in Azure Backup](https://azure.microsoft.com/en-us/updates/v2/AzBackupGrsForPv2Ultra)
- [Generally Available: Azure Elastic SAN for Azure VMware Solution](https://azure.microsoft.com/en-us/updates/v2/AzureElasticSAN-for-AVS)
- [Retirement: Older versions of EA Azure Price Sheet – Download by Billing Account API](https://azure.microsoft.com/en-us/updates/v2/Cost-Management-Download-by-Billing-Account-API-version-retirement)
- [Generally Available: App Service Environment memory intensive pricing tier](https://azure.microsoft.com/en-us/updates/v2/Announcing-App-Service-Environment-Memory-Intensive-Pricing-Tier)
- [Generally Available: Storage account default egress limit increase to 200 Gbps](https://azure.microsoft.com/en-us/updates/v2/Storage-account-default-egress-limit-increase-to-200-Gbps)
- [Retirement: Announcing upcoming retirement of custom text analytics for health (preview) in Azure AI Language](https://azure.microsoft.com/en-us/updates/v2/custom-text-analytics-for-health-retirement)
- [Retirement: Announcing upcoming retirement of custom sentiment analysis (preview) in Azure AI Language](https://azure.microsoft.com/en-us/updates/v2/custom-sentiment-analysis-retirement)
- [Generally Available: Several performance management server parameters now modifiable on Azure Database for PostgreSQL](https://azure.microsoft.com/en-us/updates/v2/performance-management-server-parameters-now-modifiable-on-Azure-Database-for-PostgreSQL)
- [Public Preview: vCore-based Azure Cosmos DB for MongoDB—up to 32 TiB storage](https://azure.microsoft.com/en-us/updates/v2/vCore-based-Azure-Cosmos-DB-for-MongoDB-up-to-32-TiB-storage)
- [Public Preview: vCore-based Azure Cosmos DB for MongoDB multishard, cross-region replication](https://azure.microsoft.com/en-us/updates/v2/mdb-vcore-repl)
- [Public Preview: vCore-based Azure Cosmos DB for MongoDB multishard clusters](https://azure.microsoft.com/en-us/updates/v2/mdb-vcore-sharding)
- [Public Preview: Azure Database for PostgreSQL – Flexible Server—support for postgresql_anonymizer extension version 1.3.2](https://azure.microsoft.com/en-us/updates/v2/Azure-Database-for-PostgreSQL-support-for-postgresql-anonymizer)
- [Public Preview: DiskANN indexing on Azure Database for PostgreSQL](https://azure.microsoft.com/en-us/updates/v2/DiskANN-indexing-on-Azure-Database-for-PostgreSQL)
- [Generally Available: Redis 7.2 on Azure Cache for Redis Enterprise](https://azure.microsoft.com/en-us/updates/v2/Redis-7-2-on-Azure-Cache-for-Redis-Enterprise)
- [Generally Available: Dedicated gateway RBAC support and a new request option](https://azure.microsoft.com/en-us/updates/v2/Dedicated-gateway-RBAC-support-and-a-new-request-option)
- [Generally Available: Azure Database for MySQL – Flexible Server flexible maintenance](https://azure.microsoft.com/en-us/updates/v2/Azure-Database-for-MySQL-Flexible-Server-flexible-maintenance)
- [Generally Available: Azure Cosmos DB Data Explorer custom column selector and filter history](https://azure.microsoft.com/en-us/updates/v2/Azure-Cosmos-DB-Data-Explorer-custom-column-selector)
- [Generally Available: Azure SQL updates for early-October 2024](https://azure.microsoft.com/en-us/updates/v2/Azure-SQL-updates-for-early-October-2024)
- [Generally Available: ExpressRoute guided configuration experience](https://azure.microsoft.com/en-us/updates/v2/ExpressRoute-guided-configuration-experience)
- [Generally Available: Private endpoint support without NVA source network address translation](https://azure.microsoft.com/en-us/updates/v2/generally-available-Private-endpoint-support-without-NVA-source-network-address-translation)
- [Retirement: End of Support Announcement for Azure Load Balancer numberOfProbes property on September 1, 2027.](https://azure.microsoft.com/en-us/updates/v2/End-of-Support-Announcement-for-Azure-Load-Balancer-numberOfProbes-property-on-1-September-2027)
- [Generally Available: Custom IPv4 Prefixes (BYOIP) can be used in a Global/Regional configuration](https://azure.microsoft.com/en-us/updates/v2/Custom-IPv4-Prefixes-BYOIP-can-be-used-in-a-Global-Regional-configuration)
- [Public Preview: Simulate everyday interactions with your app in Azure AI Studio](https://azure.microsoft.com/en-us/updates/v2/Simulate-everyday-interactions-with-your-GenAI-App-Public-Preview)
- [Public Preview: New evaluations for quality and similarity in Azure AI Studio](https://azure.microsoft.com/en-us/updates/v2/ROUGE-BLEU-METEOR-GLEU-Evaluations-Public-Preview)
- [Public Preview: Evaluations for protected material (text) in Azure AI Studio](https://azure.microsoft.com/en-us/updates/v2/Protected-Material-Text-Evaluations-Public-Preview)
- [Public Preview: Evaluations for indirect prompt injection attacks in Azure AI Studio](https://azure.microsoft.com/en-us/updates/v2/XPIA-Evaluations-Public-Preview)
- [Retirement: Azure Spring Apps will be retired on March 31, 2028](https://azure.microsoft.com/en-us/updates/v2/Azure-Spring-Apps-will-be-retired-on-March-31-2028)
- [Retirement: Azure Diagnostic Extensions set to Retire in 18 months](https://azure.microsoft.com/en-us/updates/v2/Azure-Diagnostics-Extensions-retiring-march-31-2026)
- [Generally Available: Reminder New E-mail templates for Log search alerts - API version 2021-08-01 and up](https://azure.microsoft.com/en-us/updates/v2/Azure-Alerts-LSA-Email-template-reminder)
- [Retirement: Azure Sphere is retiring Legacy service interfaces on September 27th, 2027](https://azure.microsoft.com/en-us/updates/v2/Azure-Sphere-Legacy-Interface-Retirement)
- [Public Preview: Switch to Azure Business Continuity Center for at scale BCDR management](https://azure.microsoft.com/en-us/updates/v2/Switch-to-Azure-Business-Continuity-Center-for-your-at-scale-BCDR-management-needs)
- [Generally Available: Save up to 56% on the latest Linux VMs in most Azure regions for a limited time](https://azure.microsoft.com/en-us/updates/v2/Linux-VM-promotional-offer)
- [Public Preview: Azure Virtual Network Monitoring IP address management](https://azure.microsoft.com/en-us/updates/v2/Introducing-the-Public-Preview-of-AVNM-IPAM)
- [Public Preview: Azure NVads V710 v5-series virtual machines](https://azure.microsoft.com/en-us/updates/v2/Public-preview-Azure-NVads-V710-v5-series-virtual-machines)
- [Public Preview: Azure NMads MA35D-Series virtual machines](https://azure.microsoft.com/en-us/updates/v2/Public-preview-Azure-NMads-MA35D-Series-virtual-machines)
- [Generally Available: Azure Backup- Reduced Protected Instance Fee for SAP HANA Backup](https://azure.microsoft.com/en-us/updates/v2/Azure-Backup-Reduced-Protected-Instance-Fees-HANA-Backup)
- [Retirement: SQL Data Sync will be retired on September 30th, 2027](https://azure.microsoft.com/en-us/updates/v2/SQL-Data-Sync-Retirement)
- [Retirement: Azure Orbital Ground Station Retirement](https://azure.microsoft.com/en-us/updates/v2/Azure-Orbital-Ground-Station-Retirement)
- [Retirement: End of life for NCv3-series VM family support in Azure Batch pools](https://azure.microsoft.com/en-us/updates/v2/NCv3-series-VM-family-support-in-azure-batch-pools-retirement)
- [Retirement: Planned Service Retirement - Azure Automation State Configuration on September 30, 2027](https://azure.microsoft.com/en-us/updates/v2/Planned-Service-Retirement-Azure-Automation-State-Configuration-16-September-2027)
