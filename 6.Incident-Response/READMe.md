# Phishing Incident Investigation (Case Study)

> **Note:** This case study is based on a simulated phishing investigation completed within a corporate security training environment. Specific organisational details, indicators, and sensitive information have been anonymised or removed while preserving the investigation methodology and security analysis process.

## Overview

This case study documents a simulated phishing investigation completed within a corporate security training environment.

The objective was to investigate a suspicious email, identify potential indicators of compromise (IOCs), assess the risk of credential compromise, and determine whether further security investigation was required.

The investigation followed a SOC incident response workflow:

1. Incident identification
2. Initial analysis
3. Evidence collection
4. IOC investigation
5. Identity activity review
6. Impact assessment
7. Security recommendations

---

# Incident Details

| Category | Details |
|---|---|
| Incident Type | Phishing |
| Severity | Medium |
| Status | Resolved |
| Impact | No confirmed compromise |
| Security Tools Used | Microsoft Sentinel, Microsoft Defender for Office 365, Microsoft Entra ID |

---

# Incident Summary

A user reported a suspicious email impersonating a trusted payment service provider.

The email attempted to persuade the user to verify their account through a link leading to a fake login page designed to capture credentials.

The investigation focused on:

- Determining whether the email was malicious
- Analysing email indicators and authentication results
- Identifying potential indicators of compromise
- Assessing whether credentials may have been exposed
- Reviewing identity activity for signs of account compromise

Following investigation, no evidence of successful credential compromise or additional malicious activity was identified.

---

# Initial Detection

## What Triggered the Investigation?

The investigation began after a user reported a suspicious email received within the organisation.

Initial indicators suggested the email was potentially malicious:

- Sender information did not match the legitimate organisation
- Reply-to details appeared suspicious
- The email contained a suspicious verification link
- The domain used a lookalike impersonation technique
- The message attempted to create urgency

Based on these indicators, the email was treated as a potential phishing attempt.

---

# Investigation Process

## Email Analysis

The email was analysed to determine whether it was legitimate or malicious.

The investigation included:

- Reviewing sender details
- Analysing email headers
- Checking SPF, DKIM, and DMARC authentication results
- Reviewing the sender domain
- Analysing embedded URLs
- Checking domain reputation information

### Findings

The investigation identified:

- A lookalike domain designed to impersonate a legitimate service
- Suspicious email authentication results
- A malicious link directing users towards a fake login page

---

# Indicators of Compromise (IOCs)

The investigation identified the following indicators:

| Indicator Type | Value |
|---|---|
| Domain | Redacted / Simulated phishing domain |
| Sender Address | Redacted |
| IP Address | Redacted |
| URL | Redacted phishing URL |

The identified indicators were used during the investigation to determine whether related activity existed within available security telemetry.

---

# Security Investigation

## Microsoft Sentinel

Microsoft Sentinel was used as part of the investigation workflow to:

- Review security events
- Search for related indicators
- Correlate available telemetry
- Identify possible related activity

The investigation focused on determining whether the phishing attempt resulted in additional suspicious behaviour.

---

## Microsoft Entra ID

Identity logs were reviewed to identify possible signs of account compromise, including:

- Suspicious authentication attempts
- Unusual login locations
- Failed sign-in activity
- Potential credential misuse

### Result

No evidence of successful authentication attempts or suspicious sign-in activity was identified.

---

# Response Actions

## Containment Recommendations

Recommended containment actions included:

- Blocking malicious domains
- Blocking associated indicators
- Adding indicators to security monitoring platforms
- Preventing access to phishing infrastructure

---

## Remediation Recommendations

Recommended improvements included:

- Strengthening SPF, DKIM, and DMARC policies
- Improving email filtering controls
- Increasing phishing detection coverage
- Monitoring identity activity following suspected phishing attempts
- Improving user awareness training

---

# Incident Outcome

The investigation concluded that the phishing attempt was unsuccessful.

No evidence was identified of:

- Credential compromise
- Successful authentication
- Malware execution
- Persistence
- Lateral movement

The incident was closed after confirming no additional suspicious activity was identified.

---

# Root Cause Analysis

## Why Did This Happen?

The incident relied on social engineering techniques rather than exploiting a technical vulnerability.

The attacker used:

- Email impersonation
- Lookalike domains
- Fake authentication pages
- Urgency-based messaging

The primary risk was user interaction with the phishing link and potential credential exposure.

---

# Recommendations

## Immediate Improvements

- Block identified malicious indicators
- Review email security policies
- Monitor related indicators
- Continue investigating suspicious authentication activity

---

## Long-Term Improvements

- Improve phishing awareness training
- Conduct regular phishing simulations
- Strengthen email authentication controls
- Improve detection rules and alerting coverage
- Continue threat intelligence monitoring

---

# Key Learnings

## Technical Skills Developed

This investigation helped develop experience with:

- Phishing email analysis
- Email header investigation
- SPF, DKIM, and DMARC validation
- IOC identification
- Microsoft Sentinel investigation workflows
- Microsoft Entra ID sign-in analysis
- Security event correlation

---

## Analyst Reflection

This investigation reinforced the importance of validating evidence before determining whether an account has been compromised.

A phishing alert does not automatically mean a security breach has occurred. The role of the analyst is to collect evidence, investigate related activity, determine impact, and recommend appropriate response actions.

By combining email analysis with identity monitoring, the investigation demonstrated how multiple security data sources can be used together to validate phishing incidents and support effective incident response.

---

# Tools Used

- Microsoft Sentinel
- Microsoft Defender for Office 365
- Microsoft Entra ID
- Azure Monitor