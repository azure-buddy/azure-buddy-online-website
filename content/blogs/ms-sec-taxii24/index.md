---
title: "Exchanging Threat Intelligence using TAXII in Microsoft's Unified Security Operations Platform"
date: 2025-02-23
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

***Below an logical overview of the model:***
![TAXII Logical Overview](img/taxii-model.jpg "TAXII Logical Overview")

TAXII protocol defines a set of specifications for both the `TAXII Server` and `TAXII Client` components. An `TAXII Server` instance provides supporting services and primary sharing capabilities. Supporting services that are provided are:

- **API Root** endpoint which provides a way to create a logical grouping of your sharing types, such as collections and channels.
- **Discovery** helps you to discover newly available collections through *DNS* or a specific endpoint.
- Monitor the actual `TAXII Client` requests through the **Status** endpoint.

Primary sharing capabilities are built up by two sharing models. Currently those models are:
- **TAXII Collection(s)**, which requires you to *Pull* **objects** over HTTP(S), including *optional* pagination.
- **TAXII Channel(s)**, requires you to *Publish or Subscribe to* **messages**, which provides an *event-driven* approach of exchanging TI data through *Push* messages.

Last part to look into is the `TAXII Client`. `TAXII Client` capabilities differ per sharing model. Looking into *collections*, it mainly *pulls* and *ingest* objects from collections into a local SIEM or SOAR such as `Microsoft Sentinel`. For channels it requires a *Pub/Sub* capable `TAXII Client`, for which(at the moment of writing) only a *reference implementation* is available.

## TAXII?

Abbreviation stands for Trusted Automated eXchange of Intelligence Information. 

## Goals of the TAXII Implementation standard

The main goal of the TAXII protocol is to provide a *simple*, *secure* and *scalable* way of communicating cyber threat intelligence through a set of implementation standards like *RESTful API* definitions.

Consuming *STIX Feeds* using a `TAXII Client` based on the *Collection* sharing model is commonly used practice and already implemented by many security vendors.

On the other hand, we have *channels* which are still in a more *conceptual state*. For the future of Cyber Threat Intelligence it exposes many benefits for *Threat Intelligence Platforms* like improved Performance due *efficient data handling* and greater *Reliability* and *Scalability* due the nature of an *Event-driven Architecture*. This shall enable National CERT's, CSP's or MSSP's to exchange more *TI data* near real-time and increase confidence due the possibilites of improving quality by easier reporting of *Sightings* or new *Observables*. 

In short we see that *Collections* can be seen as API's which requires a more *Pull* approach, potentially including pagination. *Channels* seem to be more of a *Pub/Sub* approach, where you only get pushed new or updated messages.

*TAXII* components are the **TAXII Server** and **TAXII Client**. Most *SIEM* and *SOAR* vendors like *Microsoft* support subscribe and ingesting TAXII based Threat Intelligence (TI) Feeds. They act as a *TAXII Client* by consuming TI Feeds. As you may expect TI objects defined using STIX, which is the common sharing model for IOC data.

*TAXII Servers* are mostly known as a *Threat Intelligence Platform* (TIP). Example *TIP* vendors are *Filigran*, *MISP and *EclecticIQ*. *Microsoft Defender for Threat Intelligence (MDTI)* does not yet support creating your own *TAXII Server*.


## Microsoft Security products with TAXII (Client) Support

- [Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/)
- [Microsoft Defender](https://learn.microsoft.com/en-us/unified-secops-platform/threat-intelligence-overview/)

The next post in the series will follow soon! Then we will dive into the `TAXII Implementation`.

Follow me or connect to learn more about STIX-TAXII?

For more great content about Azure Cloud-Native and Cloud Security, follow me or check out my other blogs at [Azure Buddy Online](https://azurebuddy.online).

To support my work, I would be more than grateful if you could repost it. 😊
