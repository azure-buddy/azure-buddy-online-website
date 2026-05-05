---
title: "Breaking the Code: Multi-Stage ‘Code of Conduct’ Phishing Campaign Leads to AiTM Token Compromise"
date: "2026-05-05"
description: "A summary of Microsoft’s latest research into a sophisticated multi-stage phishing campaign that leverages Adversary-in-the-Middle techniques to compromise session tokens and bypass MFA."
slug: "multi-stage-code-of-conduct-phishing-aitm-token-compromise"
tags: ["Cybersecurity", "Phishing", "Microsoft Security", "AiTM", "Threat Intelligence", "Identity Protection"]
---

## Breaking the code: How a multi-stage phishing campaign bypasses MFA

A recent Microsoft Security blog highlights a sophisticated phishing campaign that demonstrates how attackers are evolving beyond traditional credential theft. The campaign, themed around corporate “code of conduct” messaging, uses multiple stages to build trust and evade detection.

### What makes this campaign different?

This attack stands out due to its layered execution:

- Victims receive convincing phishing emails posing as internal policy or compliance communications  
- Attachments or links trigger a staged redirection flow  
- CAPTCHA checks are used to evade automated security analysis  
- Users are ultimately redirected to a fake authentication page mimicking legitimate sign-in portals  

This approach increases user engagement while minimizing early detection.

### The real threat: AiTM token compromise

The campaign leverages **Adversary-in-the-Middle (AiTM)** techniques. Instead of just capturing usernames and passwords, attackers intercept authentication sessions in real time.

This enables them to:

- Capture session tokens  
- Bypass multi-factor authentication (MFA)  
- Hijack active sessions  
- Maintain access even after password resets  

### Why this matters

This attack reflects a broader shift in the threat landscape:

- MFA is no longer a complete safeguard on its own  
- Session token theft is becoming a primary attacker objective  
- Attackers are increasingly using phishing-as-a-service platforms  

Once inside, attackers can move laterally, launch internal phishing campaigns, or execute business email compromise (BEC) attacks.

### Key takeaways for defenders

To defend against these advanced techniques, organizations should:

- Adopt phishing-resistant MFA (such as FIDO2 or certificate-based authentication)  
- Enforce strong Conditional Access policies  
- Monitor for unusual session behavior and token misuse  
- Invest in user awareness training focused on modern phishing tactics  
- Leverage AI-driven security and threat intelligence  

### Final thoughts

Phishing attacks are evolving rapidly. The focus has shifted from stealing credentials to stealing authenticated sessions. Organizations must adapt by strengthening identity security, improving visibility, and embracing modern detection strategies.

---

**Did you know that Azure Buddy is a Microsoft Most Valuable Professional**.
**Last years he helped several client with Cybersecurity and Observability AI challenges! and getting more value from Threat Intelligence!**  

**We love to hear more about your AI Observability and Cybersecurity challenges!**

-Azure Buddy
