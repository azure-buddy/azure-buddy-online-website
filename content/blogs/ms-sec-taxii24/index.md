---
title: "Exchanging Threat Intelligence using TAXII in Microsoft's Unified Security Operations Platform"
date: 2025-02-21
draft: false
description: "Blog about the various available TAXII integration options within Microsoft's Unified SecOps Platform products."
slug: "ms-sec-taxii24"
tags: ["blogs", "Defender", "Sentinel", "SecOps", "Cyber Security", "STIX", "TAXII", "Unified"]
series: ["Using STIX in Microsoft's Unified SecOps Platform"]
series_order: 2
---

## Introduction

🔥 This is our second part in the series on using STIX in Microsoft's Unified SecOps Platform, where we guide you through basic topics in short digestible posts. This time we'll look at the TAXII portion of the `STIX-TAXII` standard.


{{< alert >}}
This is the second post in this series, we will explain what is TAXII and explain the purpose!
{{< /alert >}}

## What is TAXII?

TAXII is an application-layer protocol that serves as a transport mechanism for sharing cyber threat intelligence.

Below an logical overview of the model:

![TAXII Logical Overview](img/taxii-model.jpg "TAXII Logical Overview")

TAXII protocol defines a set of specifications for both the `TAXII Server` and `TAXII Client` component. Two sharing models exist:
- Collection(s) to pull Objects.
- Channel(s) to subscribe to Messages.

The use of *Collections* is commonly used and implemented. Looking into the future *Channel* model seems to fill-in a gap for National CERT's, CSP's or MSSP's.

In short we see that *Collections* can be seen as API's which requires a more *Pull* approach, potentially including pagination. *Channels* seem to be more *Pub/Sub* approach, where you only get pushed new messages.

TAXII components are the **TAXII Server** and **TAXII Client**. Most *SIEM* and *SOAR* vendors like *Microsoft* support subscribe and ingesting TAXII based Threat Intelligence (TI) Feeds. They act as a *TAXII Client* by consuming TI Feeds. As you may expect TI objects defined using STIX, which is the common sharing model for IOC data.

*TAXII Servers* are mostly known as a Threat Intelligence Platform (TIP). Example *TIP* vendors are *Filigran*, *MISP and *EclecticIQ*. *Microsoft Defender for Threat Intelligence (MDTI)* does not yet support creating your own *TAXII Server*.

Microsoft Unified Security Platform.

## TAXII?

Abbreviation stands for Trusted Automated eXchange of Intelligence Information. 

## Goal of the TAXII Implmentation?

The purpose of the TAXII protocol is to provide a simple, secure and scalable way of communicating cyber threat intelligence through a standardized set of RESTful API definitions.


## Microsoft Security products with TAXII (Client) Support

- [Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/)
- [Microsoft Defender](https://learn.microsoft.com/en-us/unified-secops-platform/threat-intelligence-overview/)

The next post in the series will follow soon! Then we will dive into the `TAXII Implementation`.

Follow me or connect to learn more about STIX-TAXII?

For more great content about Azure Cloud-Native and Cloud Security, follow me or check out my other blogs at [Azure Buddy Online](https://azurebuddy.online).

To support my work, I would be more than grateful if you could repost it. 😊
