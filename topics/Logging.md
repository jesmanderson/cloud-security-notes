# Logging & Monitoring

## What Is Logging & Monitoring?
The practice of collecting, analyzing, and responding to system events to ensure security, operational visibility, and compliance.

## Key Concepts

- CloudTrail / Activity Logs: Track API calls and user activity across cloud services
- GuardDuty / Threat Detection: Detect anomalies and potential threats
- SIEM (Security Information and Event Management): Aggregate and analyze logs for - security insights
- Centralized Logging: Consolidate logs across accounts and services
- Alerting & Dashboards: Provide real-time visibility and notifications


## Goals

- Gain visibility into cloud environments
- Detect suspicious or unauthorized activity early
- Support investigations, incident response, and audits


## Best Practices

- Enable logging across all regions and services
- Send logs to centralized, immutable storage (e.g., S3 with versioning)
- Monitor for unusual patterns (e.g., root account usage, failed logins)
- Integrate logs with SIEM/SOAR tools for automated analysis and response
- Regularly test alerting workflows and incident playbooks


## Tools

- AWS CloudWatch – Metrics, logs, and alarms
- AWS GuardDuty – Threat detection
- Splunk / Wazuh – SIEM platforms for log aggregation and analysis
- Azure Sentinel – Cloud-native SIEM and SOAR
- CloudTrail / Azure Activity Logs – Track API and user actions


## Examples

- AWS Stack: CloudTrail + GuardDuty + CloudWatch → centralized S3 bucket
- Azure Stack: Activity Logs + Defender for Cloud + Log Analytics


## Practice Scenario
### Detecting a Failed Login Attempt and Triggering Alerts

- Enable CloudTrail or Azure Activity Logs
- Configure GuardDuty or Sentinel to detect failed login attempts
- Set up alerting rules in CloudWatch or Sentinel
- Route alerts to email, Slack, or SOAR platform for response
- Review logs in SIEM for context and correlation


## Mapping to Standards

- NIST 800-53: AU-2, AU-6, AU-12
- CIS Controls: 8.2, 8.7, 8.8
- SOC 2: CC7.2, CC7.3
