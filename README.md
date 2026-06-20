# Azure Monitor Alerts Lab

## Overview
This project demonstrates the configuration of Azure Monitor Alerts 
to detect performance anomalies on an Azure Virtual Machine and notify 
engineers through multiple channels before end users are impacted.

## Resource Monitored
- **Resource:** Azure Virtual Machine (B1s) — `monitor-lab-vm`
- **Resource Group:** `monitor-lab-rg`
- **Platform:** Microsoft Azure (Azure for Students)

## Metrics Selected
| Metric | Threshold | Reason |
|---|---|---|
| Percentage CPU | > 50% for 5 minutes | CPU saturation causes application slowness and timeouts |

## Alert Configuration
- **Alert Rule:** `cpu-high-alert-lab`
- **Severity:** Sev2 - Warning
- **Threshold Type:** Static
- **Evaluation Frequency:** Every 1 minute
- **Lookback Period:** 5 minutes

## Action Group
- **Name:** `lab-monitor-alerts-ag`
- **Notifications:** Email + SMS

## Alert Lifecycle
1. **Fired** — CPU exceeded 50% threshold, Action Group notified via email and SMS
2. **Acknowledged** — Alert manually acknowledged with investigation comment
3. **Resolved** — CPU dropped below threshold, resolved notification sent automatically
