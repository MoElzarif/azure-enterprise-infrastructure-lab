# 05 - Monitoring

## Purpose

Azure Monitor was configured to provide basic visibility into the lab environment.

Monitoring is important because administrators need to detect performance issues, resource usage problems, and possible service disruptions.

---

## Monitoring Components Used

| Component | Purpose |
|---|---|
| Azure Monitor | Tracks metrics and alert conditions |
| Log Analytics Workspace | Stores monitoring and log data |
| Alert Rule | Detects high CPU usage |
| Action Group | Defines who or what gets notified when an alert triggers |

---

## Alert Rule Configuration

A high CPU alert rule was configured to monitor virtual machine performance.

| Setting | Value |
|---|---|
| Alert Type | Metric alert |
| Signal | Percentage CPU |
| Condition | CPU above threshold |
| Target Resource | Azure virtual machine |
| Action Group | Configured for alert notification |
| Purpose | Detect high CPU usage on lab resources |

---

## Why CPU Monitoring Matters

CPU monitoring helps administrators identify when a virtual machine may be under heavy load.

High CPU usage can indicate:

- Application performance problems
- Misconfigured services
- Unexpected workload spikes
- Possible security issues
- Need for resizing or optimization

---

## Log Analytics Workspace

A Log Analytics Workspace was included in the lab to support centralized monitoring.

In real environments, Log Analytics can be used to collect and query:

- VM performance data
- Activity logs
- Security logs
- Diagnostic logs
- Alert data

---

## Why This Matters

Monitoring is a key part of Azure administration.

This lab demonstrates the ability to:

- Configure basic Azure Monitor alerting
- Track VM performance metrics
- Use alert rules for proactive monitoring
- Understand how administrators detect cloud infrastructure issues

---

## Evidence

The screenshot below shows the configured high CPU alert rule.

![High CPU Alert](../screenshots/monitoring/high-cpu-alert.png)

---

## Result

Azure Monitor was successfully configured with a high CPU alert rule to detect performance issues in the lab environment.
