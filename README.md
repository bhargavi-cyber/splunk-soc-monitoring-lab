# Splunk SOC Monitoring Lab

This project demonstrates how Splunk can be used to analyze log data, detect failures, visualize system activity, and generate automated alerts using SPL queries.

The lab simulates a monitoring workflow similar to what analysts perform in a Security Operations Center (SOC).

---

## Project Workflow

```
Log Events
    │
    ▼
Data Exploration
    │
    ▼
Failure Detection
    │
    ▼
Failure Pattern Analysis
    │
    ▼
Monitoring Dashboard
    │
    ▼
Automated Alert Detection
```

---

## Dashboard Overview

A monitoring dashboard was created in Splunk to visualize failure trends and system activity.

### Screenshot

<img src="screenshots/04-dashboard-overview.png" width="750">

The dashboard contains multiple panels that highlight important metrics for monitoring system behavior.

| Panel | Purpose |
|------|--------|
| Failures by User | Displays failed call activity grouped by device |
| Total Calls by Host | Shows call activity trends across hosts |
| Failure Visualization | Displays total number of network failures |
| Failures by Partner | Identifies partners generating the most failures |

To learn how the dashboard was designed, see:

➡ **[Dashboard Design](project/dashboard-design.md)**

---

## Failure Analysis

During analysis, the dataset was filtered to identify devices and IP addresses generating the most failures.

### Screenshot

<img src="screenshots/05-device-failure-analysis.png" width="750">

This analysis helps identify:

- problematic devices
- abnormal system activity
- potential service issues

More detailed investigation steps are available here:

➡ **[Project Investigation Workflow](project/project-overview.md)**

---

## Automated Alert Detection

To detect abnormal behavior automatically, an alert was configured to monitor call success rates.

### Screenshot

<img src="screenshots/06-alert-logic-query.png" width="750">

If the success rate drops below the defined threshold, the alert triggers and records the event.

Detailed explanation of the alert logic is available here:

➡ **[Alert Logic](project/alert-logic.md)**

---

## Repository Structure

```
splunk-soc-monitoring-lab
│
├── docs
│   ├── splunk-architecture.md
│   ├── splunk-data-ingestion.md
│   ├── splunk-search-and-fields.md
│   ├── splunk-spl-commands.md
│   ├── splunk-transforming-commands.md
│   └── splunk-reports-dashboards.md
│
├── project
│   ├── project-overview.md
│   ├── dashboard-design.md
│   └── alert-logic.md
│
├── queries
│   ├── data-exploration.spl
│   ├── failure-detection.spl
│   ├── host-activity-monitoring.spl
│   ├── partner-failure-analysis.spl
│   └── success-rate-monitoring.spl
│
├── screenshots
│
└── README.md
```

---

## Skills Demonstrated

| Skill | Description |
|------|-------------|
| Log Analysis | Investigating system logs using SPL queries |
| SPL Query Writing | Creating searches to filter and analyze data |
| Dashboard Creation | Visualizing system activity with Splunk dashboards |
| Alert Configuration | Detecting abnormal behavior automatically |
| Data Visualization | Using charts and metrics to monitor failures |

---

## Key Takeaway

This project demonstrates how Splunk can be used to transform raw machine data into actionable monitoring insights.

The workflow implemented in this lab mirrors how SOC analysts:

- investigate log data
- detect abnormal patterns
- visualize system activity
- automate monitoring with alerts
