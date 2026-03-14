# Alert Logic

The final step of the project was configuring an automated alert to detect abnormal behavior in the dataset.

The goal of the alert was to monitor the **call success rate** and trigger an alert when the percentage dropped below a defined threshold.

---

## Alert Detection Workflow

```
Event Logs
     │
     ▼
SPL Query
     │
     ▼
Calculate Success Rate
     │
     ▼
Threshold Check
     │
     ▼
Trigger Alert
```

---

## SPL Query Used

```
index=main sourcetype=eventgen
| stats count(responseCode) as totalAttempts
count(eval(callResult="Success")) as totalSuccess by partner
| eval callSuccessPercentage=(totalSuccess/totalAttempts)*100
| search callSuccessPercentage < 62
```

This query calculates the percentage of successful calls for each partner and filters results where the success rate falls below the defined threshold.

---

## Alert Configuration

| Setting           | Value                   |
| ----------------- | ----------------------- |
| Alert Type        | Scheduled               |
| Schedule          | Runs every hour         |
| Trigger Condition | Number of results > 0   |
| Trigger Action    | Add to Triggered Alerts |

---

## Alert Configuration Screenshot

<img src="../screenshots/alert-creation.png" width="750">

---

## Purpose

This alert allows analysts to detect abnormal drops in service performance and investigate issues before they affect users.

