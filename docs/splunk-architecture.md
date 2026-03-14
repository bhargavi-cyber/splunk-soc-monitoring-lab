# Splunk Architecture

Splunk processes machine data using a distributed architecture that consists of several core components responsible for collecting, indexing, and searching data.

---

## Architecture Overview

```
Log Sources
     │
     ▼
Forwarder
     │
     ▼
Indexer
     │
     ▼
Search Head
     │
     ▼
Dashboards & Alerts
```

This pipeline shows how log data travels through the Splunk system before becoming searchable insights.

---

## Core Splunk Components

| Component   | Role            | Description                                            |
| ----------- | --------------- | ------------------------------------------------------ |
| Forwarder   | Data Collection | Collects log data from machines and sends it to Splunk |
| Indexer     | Data Processing | Processes raw logs into searchable events              |
| Search Head | Data Analysis   | Runs search queries and generates results              |
| Dashboards  | Visualization   | Displays insights and monitoring metrics               |

---

## Forwarders

Forwarders collect data from systems and send it to the indexer.

### Types of Forwarders

| Type                | Description                                                |
| ------------------- | ---------------------------------------------------------- |
| Universal Forwarder | Lightweight agent that only collects and forwards data     |
| Heavy Forwarder     | Full Splunk instance capable of parsing and filtering data |

---

## Indexer Responsibilities

The indexer performs several tasks when processing incoming logs.

| Task                 | Description                                     |
| -------------------- | ----------------------------------------------- |
| Event Breaking       | Splits raw data into individual events          |
| Metadata Assignment  | Adds host, source, sourcetype, and index fields |
| Timestamp Extraction | Determines when events occurred                 |
| Storage              | Stores events in searchable indexes             |

---

## Data Storage Buckets

Splunk stores indexed data in buckets that represent stages in the data lifecycle.

| Bucket | Description                 |
| ------ | --------------------------- |
| Hot    | Actively receiving new data |
| Warm   | Recently indexed data       |
| Cold   | Older but searchable data   |
| Frozen | Archived or deleted data    |
| Thawed | Restored data for searching |

---

## Summary

Splunk architecture consists of three main processing components:

* Forwarders (data collection)
* Indexers (data processing and storage)
* Search Heads (searching and visualization)

Together they enable organizations to analyze machine data and detect operational or security issues efficiently.
