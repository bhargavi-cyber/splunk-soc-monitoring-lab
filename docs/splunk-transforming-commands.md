# Transforming Commands in Splunk

Transforming commands convert raw events into structured statistical tables.

---

## Data Transformation Workflow

```
Raw Events
     │
     ▼
Transforming Command
     │
     ▼
Statistics Table
     │
     ▼
Visualization
```

---

## Common Transforming Commands

| Command | Purpose                    |
| ------- | -------------------------- |
| stats   | Generate statistics        |
| top     | Show most frequent values  |
| rare    | Show least frequent values |
| table   | Display selected fields    |

---

## Statistical Functions

| Function | Description          |
| -------- | -------------------- |
| count    | Counts events        |
| dc       | Counts unique values |
| sum      | Calculates total     |
| avg      | Calculates average   |

---

## Example

```
index=main
| stats count by partner
```

---

## Summary

Transforming commands summarize large datasets and prepare them for visualization.

