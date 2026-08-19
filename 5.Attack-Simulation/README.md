# Attack Simulation & Security Validation

## Overview

This project explores how Microsoft Defender security tools can be used to detect, investigate, and validate security controls through controlled attack simulations.

The purpose of these simulations is to understand common attacker techniques from a defensive security perspective, analyse the telemetry generated during malicious activity, and evaluate how Microsoft security solutions identify and respond to threats.

The project focuses on the relationship between attacker behaviour and defensive visibility, helping develop practical skills in:

- Threat detection
- Security investigation
- Alert analysis
- MITRE ATT&CK mapping
- Security control validation

---

## Objectives

This project focuses on:

- Understanding common attacker techniques used against enterprise environments
- Learning how attacker activity appears from a defender's perspective
- Using Microsoft Defender security tools to analyse suspicious behaviour
- Reviewing security alerts and investigation data
- Mapping simulated activity to MITRE ATT&CK techniques
- Developing practical threat detection and response skills
- Identifying opportunities to improve security controls

---

## Technologies Used

- Microsoft Defender XDR
- Microsoft Defender for Cloud
- Microsoft Sentinel
- Microsoft Entra ID
- Azure Virtual Machines
- Windows Security Logs
- MITRE ATT&CK Framework

---

## Microsoft Defender XDR Foundation

Before conducting the attack simulations, I developed a foundational understanding of Microsoft Defender XDR and how it supports security operations.

The focus was on understanding how Defender XDR brings security signals together across Microsoft security products to provide a centralised view of threats, incidents, users, and devices.

I also reviewed:

- Defender XDR architecture and security signal integration
- Unified Role-Based Access Control (RBAC)
- Incident and alert investigation workflows
- Security and investigation areas within the Defender portal

### Why This Matters

For a SOC analyst, effective use of Defender XDR is not simply about identifying an alert. It requires understanding how different security signals relate to each other and using that context to determine whether activity represents a genuine threat.

This foundation provides the context for the attack simulations that follow, where I investigate how different attacker techniques appear within Defender telemetry and how those signals can support detection and investigation.

---
## Simulation Methodology

Each attack simulation will follow a defensive security validation approach:

Simulated Attack Technique → Security Telemetry Generated → Microsoft Defender Detection → Alert Investigation → Evidence Collection → Security Improvement Recommendations


The objective of each simulation is to understand:

- What attacker activity looks like in an environment
- What telemetry is generated during an attack
- How security tools detect suspicious behaviour
- How analysts investigate and respond to security events

---

## Simulated Attack Scenarios

### 1. Execution

(To be completed)

---

### 2. Credential Access

(To be completed)

---

### 3. Privilege Escalation

#### Scenario

A controlled simulation was used to investigate a **User Account Control (UAC) bypass** detected on a Windows 11 device. UAC bypass techniques can allow an attacker to execute actions with elevated privileges while avoiding normal user approval prompts.

#### Detection & Investigation

Microsoft Defender XDR generated an alert for **"UAC bypass was detected"**.

![Attack Activity](screenshots/privilege-escalation-activity.png)

![Attack Activity](screenshots/privilege-escalation-activity1.png)

I reviewed the affected device, user account, timestamp, process activity, and investigation timeline to understand what had occurred.

The activity involved `cmd.exe` and `powershell.exe`. I reviewed the available evidence and suspicious entities before using the process tree to confirm how the activity was executed and validate the detection.

![Defender Investigation](screenshots/privilege-escalation-investigation.png)

The investigation identified registry modification activity associated with the simulated attack.

#### MITRE ATT&CK

The activity was associated with:

- **T1548.002 – Bypass User Account Control**
- **T1112 – Modify Registry**

![MITRE ATT&CK Mapping](screenshots/privilege-escalation-mitre.png)

These techniques fall within the MITRE ATT&CK framework and were used to provide context for the observed activity.

#### Key Findings

- Microsoft Defender XDR detected a medium-severity UAC bypass attempt associated with privilege escalation activity.
- The affected Windows 11 device and user account were identified.
- `cmd.exe` and `powershell.exe` were involved in the activity.
- Process tree and timeline information helped validate the detection.
- Registry modification activity was identified during the investigation.

#### Security Improvements

- Apply least-privilege principles to reduce the impact of compromised accounts.
- Monitor for suspicious UAC bypass and registry modification activity.
- Investigate unexpected PowerShell and command-line activity involving privilege changes.
- Keep Microsoft Defender security protections enabled and monitor attempts to bypass them.

---

### 4. Defence Evasion

#### Scenario

A controlled simulation was used to investigate an attempt to disable Microsoft Defender Antivirus protection. The activity represented a potential Defence Evasion technique because an attacker may attempt to weaken or disable security controls to avoid detection.

#### Detection & Investigation

Microsoft Defender XDR generated a high-severity alert for an attempt to turn off Microsoft Defender Antivirus protection.

![Defender Alert](screenshots/defence-evasion-alert.png)

I reviewed the affected device, user account, timestamp, process activity, and command-line information to understand what had occurred.

![Defender Investigation](screenshots/defence-evasion-investigation.png)

The investigation showed PowerShell activity attempting to modify the Defender Antivirus configuration through a registry change. The available telemetry also provided information about the process responsible for the activity and the changes being attempted.

![Registry Investigation Evidence](screenshots/defence-evasion-registry.png)

#### MITRE ATT&CK

The activity was associated with:

- **T1562.001 – Impair Defenses: Disable or Modify Tools**
- **T1562.002 – Impair Defenses: Indicator Blocking**

![MITRE ATT&CK Mapping](screenshots/defence-evasion-mitre.png)

These techniques fall within the Defence Evasion tactic and provide context for the observed activity.

#### Key Findings

- A high-severity Defender alert identified an attempt to disable Microsoft Defender Antivirus.
- PowerShell was involved in the activity.
- The investigation identified the affected device and user account.
- Registry modification activity was associated with the attempted change.
- Defender XDR provided process, command-line, device, and user context for investigation.

#### Security Improvements

- Prevent unauthorised users from modifying Microsoft Defender Antivirus security settings.
- Monitor for attempts to disable or weaken Defender protections.
- Review PowerShell and registry activity associated with security-control changes.
- Investigate and escalate high-severity alerts involving attempts to impair security controls.

---

### 5. Lateral Movement

(To be completed)

---

## Investigation Workflow

(To be completed)

---

## Security Improvements

(To be completed)

---

## Key Learnings

(To be completed)
