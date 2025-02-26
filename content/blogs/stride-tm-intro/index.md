---
title: "Threat Modeling by Example using STRIDE"
date: 2025-02-24
draft: false
description: "An introduction in Threat Modeling using the STRIDE model"
slug: "stride-tm-intro"
tags: ["blogs", "threat", "modeling", "OWASP", "Stride", "Cybersecurity", "Security", "Process", "Introductiom", "Microsoft" ]
---

# Cybersecurity threats  became a business risk

## Introduction

Nowadays worldwide Cybersecurity attacks happen almost every 10 seconds. Attacks vary from *fishing*, *malware, *cryptojacking*, *ransomware* till *Denial of Service* and don’t soly target online companies anymore. The business risks related to these threats can be enormous. Not only from a financial view, but certainly from the *impact* on *reputation* and *trust*.

Taking the *shift-left approach* with *DevSecOps* we want to look into these potential threats as early as Development is started, before they become *Zero-Day Vulnerabilities* and learn from these. Some questions arise here:

- From a system perspective what are the business risks and related security threats introduced by the application underlying software system?
- Can we quickly identify such technical threats, take mitigation measures and continuously validate these?
- Are there any best practices, examples or other resources available to organize and support such proces?

It's all about properly organizing *Threat Modeling* sessions and how we can ensure *Threat Modeling* becomes part of the Software Delivery Lifecyle. Actually performing *Threat Modeling*, you begin to recognize what can go wrong in a software system. It helps to easily pinpoint potential issues in your design or implementation that require mitigation, whether it's during *Development* or throughout the lifetime of the Software system.

This blog is for everybody that is concerned about the Privacy, Safety and Security of their Software system.

## Software Delivery Lifecycle (SDL) towards DevSecOps

As already mentioned with *DevSecOps* want to start as early in the SDL as possible. *DevSecOps* is a *shift-left approach* based framework that has the goal to integrate Security into all SDL phases, supporting Development, Security and Operations. It's about *Shared Responsibility* and reducing the risk of releasing software with vulnerabilities.

Threat Modeling becomes an important part of *Continuous Security* and especially around *Planning and Development* of Secure Software. More about DevSecOps can be read [here](https://www.microsoft.com/en-us/security/business/security-101/what-is-devsecops)

For many years as Product Owner I've been using the *OWASP Threat Modeling Project* as blueprint for the Threat Modeling process. It provides a structured way to identify threats, get common understanding of the risks and later fix those findings in our Software system.  Let’s first look into what *OWASP Threat Modeling Project* delivers and it's leverages the *STRIDE Model* for discovering these potential threats.

# Useful Threat Modeling Resources

## OWASP Threat Modeling Project

Everyone working as engineer in the *DevOps* space is familiar with the *OWASP Top Ten for Web Applications*, but there is more. Actually composing this list needs a well-thought process to properly identifying and addressing software vulnerabilities like documented in the *OWASP Threat Modeling Project*. In short the project is built upon *Best Practices* and *Guiding Principles*.

As an open Community it provides good guidance about *Techniques*, *Methodologies* and *Tools*. Additionally real world examples are provided, so you can easily start *Threat Modeling* yourself.

Guiding principle here that it's all about Collaboration and open Discussion without focussing on vendor solutions.

As you may expect, *STRIDE* is referenced as a *Methodology* that provided a *structured way* of determining these *threats* and looking into *mitigation* techniques.

But what does *STRIDE* as mnemonic stands for?

## What is the STRIDE model

The STRIDE model is a widely used threat modeling framework, developed at **Microsoft** to identify potential security threats in software systems. The name is a mnemonic that stands for six categories called:

- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

in short **STRIDE**. But when do you choose *STRIDE* compared to others?

### Comparing the STRIDE model with Others

Besides STRIDE there are other interesting models, which all have their strengths like *DREAD* and *PASTA*.  While *DREAD* focuses on addressing high-severity concerns within computer systems first, calculating a score, *PASTA* is more evidence-based.

Did you know that *DREAD* was the previously developed threat modeling technique by Microsoft, which over-time was replaced with the more software-centric approach *STRIDE*.

### Explaining the STRIDE model Categories

Below we are going through every category. We explain them using common *generic threats*. These already help you later during *Threat Analysis*.

#### Spoofing
*Spoofing* is all about scenarios when authentication fails. We may have *unauthorized users* that want to impersonate legitimate employees to access sensitive or personal identifiable information (pii) data. Ultimate goal here is to perform actions that are only reserved/available for authorized personnel. 

Impact of *Spoofing* is that it could lead to unauthorized access to confidential data such as resident registers, manipulation of public records, or the execution of fraudulent transactions to even get a deeper understanding of the application and integrated systems.

#### Tampering
*Tampering* is commonly about harmful alterations to information, either at rest, storage or even during processing (in use). Malicious actors may want to alter datasets that the application system stores in the database or even modified transactions between components. *Tampering* is all about integrity of the application, since the impact can become huge. Think about a scenario when multiple records are corrupted, the spreading false information to support propaganda, or even manipulation of confidential data records for political gain.

#### Repudiation
*Repudiation* can be a user that denies whether a certain action did or did not take place by somebody. Somebody like an internal employee, citizen or system actor can submit or modify data. Without a proper *audit trail*, we *lack visibility*, it’s difficult to track those user actions and results in the fact we can’t validate their activities and hold the user *accountable* for their actions. Any modern workload must be able to provide such information.

### Information Disclosure
*Information disclosure* takes care about *Confidentiality*. Usual threats are that users may expose information to someone not authorized to see it. This can happen due insufficient encryption, misconfigurations on access level or application vulnerabilities. If this happens you may introduce *privacy violations*, *leakage of classified*, *sensitive data* like pii/phi or other critical information which can even *harm national security*. 

#### Denial of Service
*Denial of Service* are *well-known attacks* that *degrade the application health*. Such a *Distributed Denial of Service (DDoS)* attack's main goal is to harm the *availability* of the application. During such an attack legitimate users are impacted and can’t use these disrupted services, which results in delays and even *public trust* of the infrastructure, such as *critical services* like Government administrations, Bank accounts or other. Other more *Hacktivist* approach is *flooding websites* to degrade the service to share information.

#### Elevation of Privilege
*Elevation of Privilege* is all about gaining authorizations to compromise the system. *Elevation of Privilege* occurs when an attacker may *exploit vulnerabilities* with the intention to gain high privileges like administrative rights. When elevation succeeds, the attacker could manipulate system settings, control access to sensitive data or even cause damage to the application or the data. Imagine how this could have serious implications for the security, integrity and availability of an application. Addressing and fixing these vulnerabilities is crucial for maintaining a secure application system.

# Threat Modeling in Action

This last chapter we are going to walk through the *Threat Modeling* process and apply the *STRIDE* model against a typical web application. At the start we are going to ask ourself four key questions:

- What are we working on?
- What can go wrong?
- What are we going to do about it?
- Did we do a good enough job?

These four simple questions help us to focus, work to apply *Techniques*, such as provided by the *STRIDE model*. Most Threat Modeling Techniques will answer one or more of those questions. 
Let's quickly look into the process itself.

## Process steps

Like every process it's a good practice to have a good understanding of the steps and activities taken place. *Continuous Improvement* is key for high-quality Input and meaningful and measurable outcomes. Below we are going to look into the process.

The process is built on four steps:

- Prepare on Scope - Your Input
- Determine Threats
- Look for Countermeasures, eventually Fixes and Mitigations
- Review and assess your work - Outcome

## Scope

We always start with deciding the actual scope. A good scope is important for delivering high-quality input. Input here can be seen in the context of:

- *Use cases* that provide Business value.
- *Scenarios* of typical interactions with the system.
- List of involved *Assets* that include a brief Description and their corresponding Trust Levels.
- Data Flow Diagrams* (DFD), such as Architecture Models that include the known *Entry Points* and *Exit Points* of the system.

Below we are going to explain and show examples of *Input* we will provide during scoping.

### Data Flow Diagram (DFD)

A diagrams worth ten thousand words. Diagrams help to visualize 

-Azure Buddy
