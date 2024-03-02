---
title: "How to test your application for resilience using Azure Chaos Studio"
date: 2024-03-01
draft: false
description: "Short introduction to Chaos Engineering and Azure Chaos Studio."
slug: "intro-chaos-studio"
tags: ["tips", "tricks", "Azure Chaos Studio", "Chaos Engineering", "Chaos", "Resilience", "Testing", "Validation" , "Continuous Testing", "automation" ]
authors:
  - "avwsolutions"
---

# Introduction to Chaos Engineering

Are you aware of Chaos engineering? First we will start with a brief introduction. Chaos Engineering is a discipline that aims to enhance system resilience and reliability by deliberately introducing controlled chaos into software systems. It involves proactively injecting faults and disruptions into distributed systems to uncover weaknesses and vulnerabilities before they manifest in real-world scenarios. By subjecting systems to unexpected events, such as network failures, server crashes, or latency spikes, Chaos Engineering helps teams identify weaknesses, validate assumptions, and build confidence in the system's ability to withstand turbulent conditions. Ultimately, Chaos Engineering fosters a culture of resilience, enabling organizations to deliver more robust and dependable services to their users.

# Microsoft Azure Chaos Platform

Did you know that Microsoft recently launched a new platform for resilience validation through chaos testing. The product is called **  Azure Chaos Studio** 

But before starting to attack our application, we should ensure we have implemented a resilient application using a pattern that can handle failure. Designing for failure is an important topic of the Microsoft Azure Well-Architected Framework. 

When the application is getting developed we also have to ensure reliability and stable performance. We also have to define the state when our application is healthy. For this we can implement health measures for the application, so we can track key metrics like Service Level Indicators (SLI) and other important metrics around measuring Rate, Errors and Duration. This is the so-called RED method.

From an application owner perspective we want to ensure to keep our application within the boundaries we agreed on using a Service Level Objective (SLO), Recovery Time Objective (RTO) and Recovery Point Objective (RPO).

To measure and test all these critical factors you can use Azure Chaos Studio before real disruptive things like outages happen in Production.

# Azure Chaos Studio in practice

Chaos engineering as practice works like a scientific workflow:

- Form a hypothesis
- Perform fault injection experiments to validate it
- Analyze the results
- Make changes
- Repeat

It’s all about measuring, learning, improving and succeeding.  Main features are to support Chaos Validation and the actual Chaos Testing. 

Chaos validation is more about chaos drills and game days. This implies validating the resilience of systems with using the CI/CD pipelines to execute experiments based on hypotheses.  Chaos validation always starts on a Pilot instead of Production environments, since things can fail. When we validate a hypothesis we can easily promote chaos experiments for chaos testing. 

Chaos testing brings more operational responsibilities in an automated way. Chaos tests do run periodically either from Acceptance and Production systems with validated experiments. It’s about proving business continuity and preventing large scale outages. It can answer questions on Production systems on reliability like ; Are we still reliable or did we introduced a leak in our architecture pattern by introducing failure.

See below an overview on Azure Chaos Studio, which shows all features that are available to 

{{< carousel images="{azurechaosstudio.webp}" >}}

- Create experiments using an Azure portal UI.
- Provide an API for automation.
- Inject faults using agents ( or API).
- Ensure fault injection on application, system infrastructure and network layers.

# Learn more

If you want to know more about Chaos studio I really recommend to read the blog [Advancing Microsoft Azure Resilience with Chaos Studio](https://azure.microsoft.com/en-us/blog/advancing-microsoft-azure-resilience-with-chaos-studio/)

Otherwise just jump into the documention at [Microsoft Learn](https://learn.microsoft.com/us-us/azure/chaos-studio/)

Other questions or interested in our services, contact us through social media or Github.

Contributions or follow-up articles are more than appreciated!