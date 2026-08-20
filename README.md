# SOC IOC Threat Intelligence Automation

An automated Security Operations Center (SOC) workflow designed to enrich IP-based Indicators of Compromise (IOCs), calculate risk scores, generate security alerts, and support analyst investigation.

The project uses n8n to orchestrate threat intelligence lookups against VirusTotal and AbuseIPDB, processes the returned intelligence using custom risk-scoring logic, records investigation data in Google Sheets, and generates email alerts through Gmail.

> **Note:** This is a cybersecurity portfolio/lab project. Test alerts and investigation scenarios used in this repository are simulated and do not represent a production SOC environment.

-----------------------------------

## Project Overview

SOC analysts often need to investigate suspicious IP addresses using multiple threat intelligence sources. Performing these lookups manually can be repetitive and time-consuming.

This project demonstrates how part of the IOC triage process can be automated while retaining analyst decision-making for investigation and escalation.

The workflow performs the following process:

1. Receives an IP address through a webhook.
2. Queries VirusTotal for IP reputation information.
3. Queries AbuseIPDB for abuse intelligence.
4. Combines and normalizes the threat intelligence results.
5. Calculates a risk score based on multiple indicators.
6. Classifies the IOC as LOW, MEDIUM, HIGH, or CRITICAL.
7. Records the results in Google Sheets.
8. Generates an automated email alert.
9. Provides a dashboard for monitoring alerts and tracking analyst investigations.

---

## Architecture

The workflow integrates multiple threat intelligence and automation components to perform IOC enrichment, risk assessment, alerting, and analyst investigation.

![SOC IOC Threat Intelligence Automation Architecture](Docs/Architecture.png)
---

## Workflow Implementation

The automation was implemented in n8n using a webhook-driven workflow. Incoming IP addresses are enriched using VirusTotal and AbuseIPDB, after which the returned threat intelligence is normalized and merged.

Custom JavaScript logic calculates the IOC risk score, and a Switch node classifies the result into LOW, MEDIUM, HIGH, or CRITICAL severity levels. Investigation results are logged in Google Sheets, while severity-specific email alerts are generated automatically through Gmail.

![n8n SOC IOC Automation Workflow](Docs/n8n-workflow.png)


## Technologies Used

- n8n
- VirusTotal API
- AbuseIPDB API
- JavaScript
- REST APIs
- Webhooks
- JSON
- Google Sheets
- Gmail
- Threat Intelligence
- IOC Analysis

---

## Key Features

- Automated IP reputation enrichment
- Multi-source threat intelligence correlation
- Custom IOC risk-scoring logic
- LOW, MEDIUM, HIGH, and CRITICAL severity classification
- Automated alert logging
- Email-based SOC notifications
- SOC monitoring dashboard
- Analyst investigation status tracking
- Analyst decision recording
- Investigation notes and escalation tracking

---

## Project Status

Core workflow and SOC dashboard completed.

Additional documentation, screenshots, risk-scoring methodology, and sanitized workflow files will be added to this repository.
