# Azure Foundation

### Overview

This section establishes the Azure environment used across the Azure Security Portfolio. It provides the foundational infrastructure for logging, monitoring, and security detection using Microsoft Sentinel and Defender for Cloud.

The environment supports:

- centralised logging
- cloud security monitoring
- endpoint telemetry collection
- threat detection
- incident response workflows
- future attack simulation scenarios

This setup serves as the base platform for the Sentinel SOC, Defender for Cloud monitoring, identity security testing, and incident response labs contained in this repository.

---

## Objectives

This lab focuses on:

- Configuring foundational Azure security resources
- Deploying and configuring Log Analytics Workspace
- Enabling Microsoft Sentinel for SIEM monitoring
- Connecting Azure Virtual Machine telemetry
- Integrating security data connectors
- Configuring Windows logging and auditing
- Validating telemetry ingestion using KQL
- Preparing the environment for future detection engineering and threat hunting labs

---

## Architecture

![architecture](architecture-diagram.jpg)

---

## Environment Deployment

### 1. Azure Resource Configuration

Configure core Azure resources required for the security lab environment.

![Resource Group](screenshots/01-resource-group.png)

### 2. Log Analytics Workspace

Deploy a Log Analytics Workspace for centralised log ingestion and retention.

![Log Analytics](screenshots/02-log-analytics.png)

**Notes:** 
- *Log Analytics workspaces are essential for collecting, storing, and analysing log data from different sources to provide security insights and help detect threats.*
- *Sometimes called Microsoft Sentinel Workspace once Microsoft Sentinel is enabled on it*

### 3. Microsoft Sentinel Enablement

Enable Microsoft Sentinel for SIEM-based monitoring and detection.

![Sentinel Enabled](screenshots/03-sentinel-enabled.png)

**Notes:**

*Microsoft SOC Teams are assigned specific roles and permissions. 
Each team member is assigned either or a combination of these roles to perform their daily tasks*:

- **Microsoft Sentinel Reader** Stakeholders, SOC managers,etc
- **Microsoft Sentinel Responder** Security analysts L1, incident responders
- **Microsoft Sentinel Contributor** Security engineers L2, Fusion Analytics team members
  - Install and manage Solutions using Content Hub
  - Create and delete workbooks

- **Microsoft Sentinel Playbook Operator** Security analysts L1, Automation team members
  - Automate responses to threats with playbooks

### 4. Data Connector Integration

Configure data connectors to ingest security telemetry from Azure and Windows sources.

![Data Connectors](screenshots/04-data-connectors.png)

**Notes:** - *Data connectors send logs to Log Analytics Workspaces in MS Sentinel.*

### 5. Virtual Machine Telemetry

Validate that the Azure VM is sending security logs to Log Analytics.

![VM Telemetry](screenshots/05-vm-telemetry.png)


### 6. Windows Security Logging

Enable Windows auditing policies for security event generation.

![Windows Auditing](screenshots/06-windows-auditing.png)

### 7. KQL Validation

Run KQL queries to confirm log ingestion and visibility.

![KQL Validation](screenshots/07-kql-query.png)

---

## Key Learnings

- Learned how to deploy and configure Microsoft Sentinel, including setting up a Log Analytics workspace.
- Gained an understanding of Microsoft Sentinel roles and permissions and how they support secure access management.
- Explored Content Hub solutions and Data Connectors to bring data into Microsoft Sentinel.
- Connected and configured data sources for centralised log collection and monitoring.
- Verified and reviewed ingested logs to ensure data was being collected correctly and was ready for analysis.
- Developed a better understanding of how a cloud-based SIEM can be used to monitor and investigate security events.
