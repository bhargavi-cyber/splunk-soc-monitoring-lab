# Alert Logic

This section explains how an automated alert was created in Splunk to detect abnormal system behavior.
The goal of the alert is to monitor the **call success percentage for each partner** and trigger an alert when the success rate falls below the defined threshold.

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

This workflow represents how the system automatically detects abnormal performance.

---

## Step 1 — Creating the Detection Query

The first step was writing an SPL query to calculate the call success percentage.

```
index=main sourcetype="eventgen"
| stats count(responseCode) as totalAttempts count(eval(callResult="Success")) as totalSuccess by partner
| eval callSuccessPercentage=(totalSuccess/totalAttempts)*100
| search callSuccessPercentage < 62
```

### Query Explanation

| Command  | Purpose                                    |
| -------- | ------------------------------------------ |
| `stats`  | Counts total attempts and successful calls |
| `eval`   | Calculates success percentage              |
| `search` | Filters results below the threshold        |

This query identifies partners where the **call success rate drops below 62%**, which may indicate service degradation.

---

## Query Execution

The query was executed inside the Splunk Search & Reporting interface to verify the results.

<img src="../screenshots/06-alert-logic-query.png" width="750">

The results show:

* partner name
* total call attempts
* total successful calls
* calculated success percentage

This confirms the SPL query correctly identifies abnormal success rates.

---

## Step 2 — Converting Search Into Alert

After validating the query results, the search was converted into an alert using the **Save As → Alert** option.

<img src="../screenshots/07-alert-save-option.png" width="750">

This allows the query to run automatically on a schedule.

---

## Step 3 — Alert Configuration

The alert configuration window allows defining the alert schedule and behavior.

<img src="../screenshots/08-alert-configuration.png" width="750">

### Alert Settings

| Setting    | Value                                           |
| ---------- | ----------------------------------------------- |
| Alert Name | Technology_Alert_HourlyCallSuccessPercbypartner |
| Alert Type | Scheduled                                       |
| Schedule   | Run every hour                                  |
| Trigger    | Number of results > 0                           |

The alert runs every hour and checks if any partner has a success rate below the defined threshold.

---

## Step 4 — Trigger Condition

The trigger condition determines when the alert activates.

<img src="../screenshots/09-alert-trigger-condition.png" width="750">

### Trigger Logic

| Condition             | Meaning                                   |
| --------------------- | ----------------------------------------- |
| Number of Results > 0 | At least one partner has low success rate |

If the query returns any result, the alert is triggered and added to the **Triggered Alerts** list.

---

## Purpose of the Alert

This alert provides automated monitoring of call performance.

It helps analysts:

* detect abnormal service behavior
* identify failing partners
* respond quickly to performance issues

---

## Summary

The alert implementation demonstrates how Splunk can be used for automated monitoring.

The process involved:

* writing an SPL query to calculate call success rates
* validating the query results
* converting the search into a scheduled alert
* defining trigger conditions

This setup enables proactive detection of service degradation within the system.
