---
title: "Azure Buddy Monthly recap: August 2024"
date: 2024-08-02
draft: false
description: "Monthly recap of Azure updates."
slug: "update-aug-2024"
tags: ["blogs", "azure", "updates", "monthly", "security", "containers", "management"]
series: ["Monthly recap of Azure updates"]
series_order: 8
---

# Monthly recap of Azure updates 

An easy-to-scan roundup of our newest, most important highlights. Let's have a look what interested Azure updates are share. Read carefully through the updates, especially the products and support that are announced as becoming `retired`.

Again a month of `retired` services like around **Azure Logic Apps** and deprecation of outdated security protocols, like `TLS 1.0` and `TLS 1.1`.

Most important is about `requiring multifactor` based authentication for tenant. Users must use multifactor authentication (MFA) to sign into the **Azure portal**, **Microsoft Entra admin center**, and **Intune admin center**. To ensure your users can maintain access, you’ll need to enable MFA by 15 October 2024. 

## Top 5 you don't want to miss

1. Personally waiting for this moment. **Azure CNI Overlay dual-stack with Azure CNI powered by Cilium** is now in `Public Preview` for Linux based **AKS** clusters.
2. *FedRAMP* requires to be compliant with the **FIPS 140-2** standard. **AKS Node Pools** now support `FIPS mutability` to provide enhanced security. To testdrive this new feature, ensure you use the correct `OS SKU`.
3. Another Security Improvement went `GA`. **Azure Database for MySQL - Flexible Server** can now leverage `HSM-backed encryption keys` to protect data at rest. Great when requiring `enhanced encryption` using `Customer Managed Keys`.
4. Always waiting for queries complete when troubleshooting **Application Gateway**?. Not anymore, since dedicated and optimized tables are provided to store and query tge logs. The resource specific tables allow for better data manipulation and enhanced performance. This feature is now in `Generally Available`.
5. `Public Preview` now makes it possible to specify multiple different VM sizes and an allocation strategy in **Virtual Machine Scale Sets** with flexible orchestration mode. Awesome longwaiting feature.

Look at the comprehensive list below for more information.

## Azure updates

- [Public Preview – Managed linting support in API Center](https://azure.microsoft.com/en-us/updates/v2/Managed-linting-support-in-API-Center)
- [Generally Available: Azure Red Hat OpenShift Now Supports Clusters Up to 250 Nodes](https://azure.microsoft.com/en-us/updates/v2/Azure-Red-Hat-OpenShift-Now-Supports-Clusters-Up-to-250-Nodes)
- [Retirement: Azure API Management STV1 compute platform is retired as of August 31, 2024](https://azure.microsoft.com/en-us/updates/v2/Retirement-API-Management-STV1-1)
- [Retirement: Azure Logic Apps Integration Service Environment is retired as of August 31, 2024](https://azure.microsoft.com/en-us/updates/v2/ise-retirement-1)
- [Retirement: Azure HDInsight on AKS will retire on January 31, 2025](https://azure.microsoft.com/en-us/updates/v2/Azure-HDInsight-on-AKS-Retirement)
- [Generally Available: Larger Enterprise tier cache instances for Azure Cache for Redis](https://azure.microsoft.com/en-us/updates/v2/Larger-Enterprise-tier-cache-instances-for-Azure-Cache-for-Redis)
- [Retirement: Migrating to TLS 1.2+ with the Deprecation of Outdated Security Protocols](https://azure.microsoft.com/en-us/updates/v2/migrating-to-TLS-12-with-deprecation-of-outdated-security-protocols)
- [Retirement: Azure Monitor experience (preview) in HDInsight is retiring by February 1, 2025](https://azure.microsoft.com/en-us/updates/v2/HDInsight-Azure-Monitor-experience-retirement)
- [Public Preview:  JavaScript (JS) Challenge on Azure WAF integrated with Azure Front Door](https://azure.microsoft.com/en-us/updates/v2/Public-Preview-JavaScript-JS-Challenge-on-Azure-WAF-integrated-with-Azure-Front-Door)
- [General Available: Azure NetApp Files storage with cool access for all service levels](https://azure.microsoft.com/en-us/updates/v2/ANF-Cool-Access)
- [Generally Available: Workspaces in Azure API Management](https://azure.microsoft.com/en-us/updates/v2/Workspaces-in-Azure-API-Management)
- [Public Preview: Instance Mix on Virtual Machine Scale Sets](https://azure.microsoft.com/en-us/updates/v2/Instance-Mix-on-Virtual-Machine-Scale-Sets)
- [Generally Available: Attach and detach of VMs on Virtual Machine Scale Sets for a single fault domain](https://azure.microsoft.com/en-us/updates/v2/GA-attach-detach-VMSS-fault-domain-equals-1)
- [Generally Available: Azure Sphere (Integrated) announces Locate Device feature](https://azure.microsoft.com/en-us/updates/v2/Azure-Sphere-Locate-Device)
- [Retirement: Azure API Management STV1 compute platform is retired as of August 31, 2024](https://azure.microsoft.com/en-us/updates/v2/Retirement-API-Management-STV1)
- [Retirement: Azure Logic Apps Integration Service Environment is retired as of August 31, 2024](https://azure.microsoft.com/en-us/updates/v2/ise-retirement)
- [Public Preview: Customer managed planned failover for Azure Storage](https://azure.microsoft.com/en-us/updates/v2/public-preview-customer-managed-planned-failover)
- [Retirement: Azure App Service Environment v1/v2 will be retired on 31 August 2024](https://azure.microsoft.com/en-us/updates/v2/App-Service-Environment-v1v2-Retirement-Update)
- [Public Preview: Private registry support in Azure Deployment Environments](https://azure.microsoft.com/en-us/updates/v2/Private-registry-support-in-Azure-Deployment-Environments)
- [Public Preview: Azure NetApp Files now supports 50 GiB minimum volume sizes](https://azure.microsoft.com/en-us/updates/v2/Volume-enhancements)
- [Generally Available: Dedicated log analytics tables in Application Gateway](https://azure.microsoft.com/en-us/updates/v2/Dedicated-log-analytics-tables-in-Application-Gateway)
- [Generally Available: Cross Region Restore of SQL and HANA database backups from a vault with Private Endpoints enabled](https://azure.microsoft.com/en-us/updates/v2/Cross-Region-Restore-of-SQL-and-HANA-database-backups)
- [Retirement: Upcoming TLS changes for Azure Event Grid](https://azure.microsoft.com/en-us/updates/v2/TLS-changes-for-Azure-Event-Grid)
- [Generally Available: Double encryption at-rest for Azure NetApp Files](https://azure.microsoft.com/en-us/updates/v2/ANF-Double-Encryption-at-rest)
- [Public Preview: FIPS mutability support in AKS](https://azure.microsoft.com/en-us/updates/v2/FIPS-mutability-support-in-AKS)
- [Public Preview: Azure CNI Powered by Cilium & Azure CNI Overlay support in AKS](https://azure.microsoft.com/en-us/updates/v2/CNI-Powered-by-Cilium-Azure-CNI-Overlay-support-AKS)
- [Public Preview: Azure CNI overlay Windows support in AKS](https://azure.microsoft.com/en-us/updates/v2/Azure-CNI-overlay-Windows-support-in-AKS)
- [Generally Available: New features in AKS extension for Visual Studio Code](https://azure.microsoft.com/en-us/updates/v2/New-features-in-AKS-extension-for-Visual-Studio-Code)
- [Generally Available: Enable multifactor authentication for your tenant by 15 October 2024](https://azure.microsoft.com/en-us/updates/v2/Enable-multifactor-authentication-for-your-tenant-by-15-October-2024)
- [Generally Available: Azure Chaos Studio supports a new Network Isolation fault for virtual machines](https://azure.microsoft.com/en-us/updates/v2/generally-available-azure-chaos-studio-supports-a-new-network-isolation-fault-for-virtual-machines)
- [Retirement: Azure Synapse Runtime for Apache Spark 3.2 disablement](https://azure.microsoft.com/en-us/updates/v2/Azure-Synapse-Runtime-for-Apache-Spark-3-2-disablement)
- [Public Preview: High Scale mode for Azure Monitor – Container Insights](https://azure.microsoft.com/en-us/updates/v2/High-Scale-mode-Container-Insights)
- [Generally Available: Terraform support for geo-restore in Azure Database for PostgreSQL - Flexible Server](https://azure.microsoft.com/en-us/updates/v2/Terraform-support-for-geo-restore-in-Azure-Database-for-PostgreSQL-Flexible-Server)
- [Generally Available: Enforce passwordless authentication with Azure Cache for Redis](https://azure.microsoft.com/en-us/updates/v2/Enforce-passwordless-authentication-with-Azure-Cache-for-Redis)
- [Generally Available: Azure Policy support for Azure Database for PostgreSQL - Flexible Server](https://azure.microsoft.com/en-us/updates/v2/Azure-Policy-support-for-Azure-Database-for-PostgreSQL-Flexible-Server)
- [Generally Available: Navigate your data more easily in Azure Cosmos DB Data Explorer](https://azure.microsoft.com/en-us/updates/v2/Navigate-your-data-more-easily-in-Azure-Cosmos-DB-Data-Explorer)
- [Generally Available: Azure SQL updates for mid-August 2024](https://azure.microsoft.com/en-us/updates/v2/Azure-SQL-updates-for-mid-August-2024)
- [General Availability: Azure Database for MySQL Flexible Server supports Managed HSM](https://azure.microsoft.com/en-us/updates/v2/Azure-Database-for-MySQL-Flexible-Server-supports-Managed-HSM)
- [Generally Available: Dev Containers templates for Azure SQL Database](https://azure.microsoft.com/en-us/updates/v2/Dev-Containers-templates-for-Azure-SQL-Database)
- [Public Preview: Los Angeles - Azure Extended Zones](https://azure.microsoft.com/en-us/updates/v2/Los-Angeles-Azure-Extended-Zones)
- [Generally Available: Azure NetApp Files cross-zone replication](https://azure.microsoft.com/en-us/updates/v2/Cross-Zone-Replications)
- [Generally Available: Azure NetApp Files zone volume placement enhancement – Populate existing volume](https://azure.microsoft.com/en-us/updates/v2/ANF-AZ-Volume-Placement-Exisiting)
- [Generally Available: Operator and CRD support with Azure Monitor managed service for Prometheus](https://azure.microsoft.com/en-us/updates/v2/crd-support-with-azure-managed-prometheus)
- [Retirement: Azure Synapse Runtime for Apache Spark 3.1 disablement](https://azure.microsoft.com/en-us/updates/v2/Azure-Synapse-Runtime-for-Apache-Spark-3-1-Disablement)
- [Public Preview: Pre-release version - Azure API Center Visual Studio Code extension now adding a pre-release version](https://azure.microsoft.com/en-us/updates/v2/Azure-API-Center-Visual-Studio-Code-Extension-Pre-release)
- [Generally Available: Model fine-tuning support for Kubernetes AI Toolchain Operator (KAITO)](https://azure.microsoft.com/en-us/updates/v2/Model-fine-tuning-support-for-Kubernetes-AI-Toolchain-Operator)
- [Generally Available: OS SKU in-place migration for AKS](https://azure.microsoft.com/en-us/updates/v2/OS-SKU-in-place-migration-for-AKS)
- [Public Preview: Windows Annual Channel on AKS](https://azure.microsoft.com/en-us/updates/v2/Windows-Annual-Channel-on-AKS)
- [Generally Available: App Configuration references on App Service](https://azure.microsoft.com/en-us/updates/v2/app-config-ref-ga)
- [Public Preview: Azure NetApp Files volume encryption key transition](https://azure.microsoft.com/en-us/updates/v2/ANF-CMK-Transitions)
- [Public Preview: Azure Carbon Optimization](https://azure.microsoft.com/en-us/updates/v2/Carbon-Optimization)
- [Generally Available: Azure Blob Storage Lifecycle Management now supports improved control on archiving](https://azure.microsoft.com/en-us/updates/v2/lifecycle-management)
- [Generally Available: Azure Container Storage for Ephemeral (Local NVMe/Temp SSD) and Azure Disk](https://azure.microsoft.com/en-us/updates/v2/Azure-Container-Storage-GA)
- [Generally Available: IT Service Management Connector (ITSMC) is now certified with ServiceNow Washington version](https://azure.microsoft.com/en-us/updates/v2/ga-it-service-management-connector-itsmc-is-now-certified-with-servicenow-washington-version)
- [Retirement: Azure Synapse Runtime for Apache Spark 2.4 Disablement](https://azure.microsoft.com/en-us/updates/v2/Azure-Synapse-Runtime-for-Apche-Spark-2-4-Disablement)
- [Generally Available: vCore-based Azure Cosmos DB for MongoDB integration with Semantic Kernel (.NET)](https://azure.microsoft.com/en-us/updates/v2/vCore-based-Azure-Cosmos-DB-for-MongoDB-integration-with-Semantic-Kernel)
- [Public Preview: Long-term retention for CMK-enabled Azure Database for PostgreSQL - Flexible Server](https://azure.microsoft.com/en-us/updates/v2/Long-term-retention-for-CMK-enabled-Azure-Database-for-PostgreSQL-flexible-Server)
- [Generally Available: Storage autogrow replica support](https://azure.microsoft.com/en-us/updates/v2/Storage-autogrow-replica-support)
- [Generally Available: Vaulted backup for Azure Blob Storage](https://azure.microsoft.com/en-us/updates/v2/ga-vaulted-backup-azure-blob-storage)
- [Retirement: Upgrade your Azure Logic Apps Integration Service Environment workloads](https://azure.microsoft.com/en-us/updates/v2/Retirement-Upgrade-your-Azure-Logic-Apps-Integration-Service-Environment-workloads)
- [Retirement: Upgrade from Azure API Management stv1 to stv2 by Aug. 31, 2024](https://azure.microsoft.com/en-us/updates/v2/Retirement-Upgrade-from-Azure-API-Management-stv1-to-stv2)
- [Public Preview: Azure API Management WordPress plugin enables customers to build highly customizable developer portals](https://azure.microsoft.com/en-us/updates/v2/Azure-API-Management-WordPress-plugin)
