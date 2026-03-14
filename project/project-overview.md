# Project Overview

This project demonstrates how Splunk can be used to analyze machine data, detect failures, and monitor system activity using SPL queries.

The dataset used in this lab was generated using the Splunk Eventgen application to simulate real system logs.

---

## Project Workflow

```
Log Data
     │
     ▼
Data Exploration
     │
     ▼
Failure Detection
     │
     ▼
Dashboard Visualization
     │
     ▼
Automated Alerting
```

---

## Data Exploration

The first step of the project was exploring the dataset to understand the available fields and event structure.

Example query used:

```
index=main sourcetype="eventgen"
```

This query allowed identification of important fields such as:

* callResult
* partner
* deviceMAC
* nodeName

---

## Failure Detection

To detect failed events in the dataset, the following query was used:

```
index=main sourcetype="eventgen" callResult=Failure
```

This query filters events where the call result indicates a failure.

---

## Failure Analysis

The dataset was further analyzed to identify which partners generated the most failures.

```
index=main sourcetype="eventgen" callResult=Failure
| top partner
```

---

## Query Result Screenshot

<img src="../screenshots/failure-query.png" width="750">

---

## Outcome

The project demonstrates how Splunk can be used to:

* Explore machine data
* Detect abnormal patterns
* Visualize system activity
* Automate monitoring through alerts

