# Alert Logic

After building the monitoring dashboard, an automated alert was created to detect abnormal system behavior.

The objective of the alert is to monitor the **call success rate for each partner** and trigger a notification when the success percentage drops below a defined threshold.

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

## Detection Query

The alert is based on an SPL query that calculates the success rate of calls for each partner.

### SPL Query

```
index=main sourcetype="eventgen"
| stats count(responseCode) as totalAttempts count(eval(callResult="Success")) as totalSuccess by partner
| eval callSuccessPercentage=(totalSuccess/totalAttempts)*100
| search callSuccessPercentage < 62
```

This query calculates the percentage of successful calls for each partner and filters results where the success rate falls below the defined threshold.

### Screenshot

<img src="../screenshots/06-alert-logic-query.png" width="750">

---

## Alert Configuration

The alert was configured to run automatically on a schedule.

| Setting | Value |
|------|------|
| Alert Type | Scheduled |
| Schedule | Runs every hour |
| Trigger Condition | Number of results > 0 |
| Trigger Action | Add to Triggered Alerts, Log Event |

---

## Alert Actions

When the alert triggers, predefined actions are executed.

### Screenshot

<img src="../screenshots/07-alert-actions-configuration.png" width="750">

| Action | Description |
|------|-------------|
| Add to Triggered Alerts | Displays the alert in Splunk's alert manager |
| Log Event | Records the alert event in the Splunk index |

---

## Alert Summary

The final alert configuration confirms that the detection logic is active and scheduled.

### Screenshot

<img src="../screenshots/08-alert-summary.png" width="750">

This alert enables automated monitoring and helps analysts detect abnormal drops in system performance without manually checking dashboards.
