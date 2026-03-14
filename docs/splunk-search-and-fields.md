# Splunk Search Processing Language (SPL)

SPL is used to retrieve and analyze data in Splunk.

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

| Component    | Purpose                      |
| ------------ | ---------------------------- |
| Search Terms | Retrieve events              |
| Commands     | Process results              |
| Functions    | Perform calculations         |
| Arguments    | Provide parameters           |
| Clauses      | Define grouping and renaming |

---

## Common SPL Commands

| Command | Purpose                   |
| ------- | ------------------------- |
| fields  | Include or exclude fields |
| table   | Display results as table  |
| rename  | Rename fields             |
| sort    | Sort results              |
| dedupe  | Remove duplicate events   |

---

## Example SPL Query

```
index=main sourcetype=eventgen
| stats count by partner
```

---

## Summary

SPL enables analysts to retrieve, transform, and analyze log data efficiently.

