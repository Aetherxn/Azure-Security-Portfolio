# Case Study 1 - Phishing Incident Investigation

## Overview

This case study documents the investigation of a simulated phishing incident within an Azure security environment.

The objective was to investigate a suspicious email reported by a user, identify indicators of compromise (IOCs), determine whether any accounts were affected, and validate whether additional malicious activity occurred.

The investigation followed a basic SOC incident response workflow:

1. Alert identification
2. Initial analysis
3. Evidence collection
4. IOC investigation
5. Identity log correlation
6. Containment recommendations
7. Lessons learned

---

# Incident Details

| Category | Details |
|---|---|
| Incident Type | Phishing |
| Severity | Medium |
| Status | Resolved |
| Affected Systems | No confirmed compromise |
| Primary Tools Used | Microsoft Sentinel, Microsoft Defender for Office 365, Microsoft Entra ID, Azure Monitor |

---

# Incident Summary

A user reported a suspicious email that appeared to come from a trusted payment service provider.

The email attempted to convince the user to verify their account through a link leading to a fake login page. The purpose of the page was to capture user credentials.

The investigation focused on:

- Validating whether the email was malicious
- Analysing email authentication results
- Identifying malicious indicators
- Checking whether users interacted with the phishing link
- Reviewing identity logs for possible account compromise

After investigation, no evidence of successful credential theft, suspicious sign-ins, or further attacker activity was identified.

---

# Initial Detection

## What Triggered the Investigation?

The investigation was triggered after a user reported a suspicious email received in their inbox.

During initial review, several indicators suggested the email was potentially malicious:

- Sender domain did not match the legitimate organisation
- Reply-to address was different from the sender address
- The email contained a suspicious account verification link
- The domain used a lookalike naming technique (typosquatting)
- The message attempted to create urgency for the user

Based on these indicators, the email was treated as a potential phishing attempt.

---

# Investigation Process

## Email Analysis

The email was analysed to determine whether it was legitimate or malicious.

The following checks were performed:

- Reviewed sender information
- Analysed email headers
- Checked SPF, DKIM, and DMARC results
- Compared sender domain with the legitimate organisation
- Examined the embedded URL
- Reviewed domain reputation information

### Findings

The investigation identified that:

- The sender domain was a lookalike domain created to impersonate a trusted service provider.
- Email authentication checks showed suspicious results.
- The embedded URL redirected users to a fake login page designed to capture credentials.

---

# Indicators of Compromise (IOCs)

| Indicator Type | Value |
|---|---|
| Malicious Domain | secure-payments-login[.]com |
| Sender Email | support@secure-payments-login[.]com |
| IP Address | 185.xx.xx.xx |
| URL Path | /verify/account/login |

These indicators were reviewed and used for further investigation within Microsoft security tools.

---

# Azure Security Investigation

## Microsoft Sentinel

Microsoft Sentinel was used to:

- Review security alerts
- Search for related indicators
- Correlate available security telemetry
- Validate whether additional suspicious activity occurred

The identified indicators were searched across available logs to determine if the phishing attempt was connected to any other activity.

---

## Microsoft Entra ID

Entra ID sign-in logs were reviewed to identify:

- Suspicious authentication attempts
- Unusual login locations
- Failed sign-in activity
- Possible credential compromise

### Result

No successful authentication attempts or suspicious sign-in activity were identified.

---

# Response Actions

## Containment

The following containment actions were recommended:

- Block malicious domain
- Block associated IP addresses
- Add indicators to threat intelligence monitoring
- Prevent further access to the phishing infrastructure

---

## Remediation

Security improvements identified during the investigation included:

- Strengthening SPF, DKIM, and DMARC policies
- Improving email filtering rules
- Creating Sentinel analytics rules for phishing indicators
- Monitoring authentication activity associated with phishing attempts
- Increasing user awareness around phishing techniques

---

# Incident Outcome

The investigation concluded that the phishing attempt was unsuccessful.

The attacker infrastructure was identified and appropriate blocking actions were recommended.

No evidence was found of:

- Credential compromise
- Successful user authentication
- Malware execution
- Persistence
- Lateral movement

The incident was closed after confirming no further suspicious activity was present.

---

# Root Cause Analysis

## Why Did This Happen?

The attack relied on social engineering rather than exploiting a technical vulnerability.

The attacker used:

- A convincing email impersonation technique
- A lookalike domain
- A fake login page
- Urgency-based messaging

The main risk was user interaction with the phishing link and potential credential exposure.

---

# Recommendations

## Immediate Improvements

- Block identified malicious domains and IP addresses
- Review email security policies
- Monitor related indicators in Sentinel
- Continue reviewing suspicious authentication activity

---

## Long-Term Improvements

- Improve phishing awareness training
- Conduct regular phishing simulations
- Strengthen email authentication controls
- Develop additional Sentinel detection rules
- Continue improving threat intelligence monitoring

---

# Key Learnings

## Technical Skills Developed

During this investigation, I gained practical experience with:

- Phishing email analysis
- Email header investigation
- SPF, DKIM, and DMARC validation
- IOC extraction
- Microsoft Sentinel investigation workflows
- Microsoft Entra ID sign-in log analysis
- Correlating security events across Microsoft security tools

---

## Analyst Reflection

This investigation helped me understand the importance of validating evidence before determining whether an account has been compromised.

A phishing alert does not automatically mean a breach has occurred. As an analyst, the goal is to collect evidence, investigate related activity, and determine the actual impact.

By combining email analysis with identity monitoring, I was able to confirm that the phishing attempt did not result in account compromise and identify improvements that could strengthen future detection and response.

---

# Tools Used

- Microsoft Sentinel
- Microsoft Defender for Office 365
- Microsoft Entra ID
- Azure Monitor