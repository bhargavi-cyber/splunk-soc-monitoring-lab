# Splunk Search Processing Language (SPL)

SPL is used to search, filter, and analyze data in Splunk.

---

## SPL Search Pipeline

```
Search Terms
     │
     ▼
Command
     │
     ▼
Transformation
     │
     ▼
Results
```

---

## SPL Components

| Component    | Purpose                     |
| ------------ | --------------------------- |
| Search Terms | Retrieve events             |
| Commands     | Process results             |
| Functions    | Perform calculations        |
| Arguments    | Provide parameters          |
| Clauses      | Define grouping or renaming |

---

## Common SPL Commands

| Command | Purpose                         |
| ------- | ------------------------------- |
| fields  | Include or exclude fields       |
| table   | Display results in table format |
| rename  | Rename fields                   |
| sort    | Sort results                    |
| dedupe  | Remove duplicate events         |

---

## Example Query

```
index=main sourcetype=eventgen
| stats count by partner
```

---

## Summary

SPL enables analysts to retrieve, process, and visualize machine data using a pipeline-based query language.
