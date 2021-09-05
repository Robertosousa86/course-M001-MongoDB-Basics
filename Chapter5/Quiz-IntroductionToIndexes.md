# Quiz: Introduction to indexes

## Problem:
- Jameela often queries the sample_training.routes collection by the src_airport field like this:

```bash
db.routes.find({ "src_airport": "MUC" }).pretty()
```

- Which command will create an index that will support this query?

## Answer

```bash
db.routes.createIndex({ "src_airport": -1 })
```
**It doesn't really matter whether the index was created in increasing or decreasing order when it is a simple single-field index.**
