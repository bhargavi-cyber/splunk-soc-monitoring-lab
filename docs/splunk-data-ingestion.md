# Splunk Data Ingestion

Data ingestion is the process of collecting machine data and preparing it for analysis.

---

## Index Time Process

```
Input Phase
     │
     ▼
Parsing Phase
     │
     ▼
Indexing Phase
```

---

## Data Processing Stages

| Stage    | Description                                          |
| -------- | ---------------------------------------------------- |
| Input    | Splunk reads raw data from files or streams          |
| Parsing  | Data is broken into events and metadata is extracted |
| Indexing | Events are stored and made searchable                |

---

## Metadata Fields

| Field      | Description                  |
| ---------- | ---------------------------- |
| host       | Machine generating the data  |
| source     | Original location of the log |
| sourcetype | Format of the log data       |
| index      | Storage location in Splunk   |

---

## Methods of Adding Data

| Method     | Use Case                                |
| ---------- | --------------------------------------- |
| Upload     | One-time data upload                    |
| Monitor    | Continuous file monitoring              |
| Forwarding | Remote data collection using forwarders |

---

## Summary

The index-time pipeline ensures that raw machine data becomes structured and searchable within Splunk.

