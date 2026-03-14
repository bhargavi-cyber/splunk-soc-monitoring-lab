# Searching and Fields in Splunk

Fields provide structure to raw machine data and allow efficient searching.

---

## Search Workflow

```
Search Query
     │
     ▼
Field Extraction
     │
     ▼
Filtered Results
```

---

## Metadata Fields

| Field      | Purpose              |
| ---------- | -------------------- |
| host       | Source machine       |
| source     | File or log location |
| sourcetype | Format of data       |
| index      | Storage location     |

---

## Field Categories

| Category           | Description                 |
| ------------------ | --------------------------- |
| Selected Fields    | Always shown in results     |
| Interesting Fields | Frequently appearing fields |
| All Fields         | Complete field list         |

---

## Summary

Fields allow Splunk to organize machine data and make searches more efficient.
