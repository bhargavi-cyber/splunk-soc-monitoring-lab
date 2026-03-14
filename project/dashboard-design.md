# Dashboard Design

A monitoring dashboard was created to visualize system activity and detect patterns in the dataset.

The dashboard combines multiple panels that highlight key metrics related to call activity and failures.

---

## Dashboard Workflow

```
Event Logs
     │
     ▼
SPL Queries
     │
     ▼
Statistics Tables
     │
     ▼
Dashboard Panels
```

---

## Dashboard Panels

| Panel                  | Purpose                                                       |
| ---------------------- | ------------------------------------------------------------- |
| Failures by User       | Displays the number of failed calls associated with each user |
| Total Calls by Host    | Shows call activity by host system                            |
| Total Network Failures | Displays the total number of failures in the dataset          |
| Failures by Partner    | Identifies partners generating the most failures              |

---

## Dashboard Screenshot

<img src="../screenshots/dashboard-overview.png" width="750">

---

## Visualization Example

Single-value visualization was used to highlight the total number of failures detected in the dataset.

<img src="../screenshots/single-value-metric.png" width="750">

---

## Purpose

The dashboard allows analysts to quickly identify patterns and investigate abnormal activity within the system.

