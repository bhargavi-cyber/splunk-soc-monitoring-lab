# Searching and Fields in Splunk

Fields help structure raw machine data and make searches faster and more efficient.

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

| Field      | Purpose             |
| ---------- | ------------------- |
| host       | Source machine      |
| source     | File or data source |
| sourcetype | Format of data      |
| index      | Storage location    |

---

## Field Types

| Field Category     | Description                        |
| ------------------ | ---------------------------------- |
| Selected Fields    | Always shown in results            |
| Interesting Fields | Frequently appearing fields        |
| All Fields         | Complete list of fields in dataset |

---

## Field Extraction Types

| Type        | Description                |
| ----------- | -------------------------- |
| Index-time  | Extracted during indexing  |
| Search-time | Extracted during searches  |
| Ad-hoc      | Temporary field extraction |

---

## Summary

Fields provide structure to raw logs and enable efficient searching and analysis.
