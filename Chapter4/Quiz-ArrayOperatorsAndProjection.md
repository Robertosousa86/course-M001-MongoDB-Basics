# Quiz: Array operators and projection

## Problem:
- Which of the following queries will return only the names of companies from the sample_training.companies collection that had exactly 8 funding rounds?

## Answer

```bash
db.companies.find({ "funding_rounds": { "$size": 8 } },
                  { "name": 1, "_id": 0 })
```

**Since we are looking to only view the names of companies then we have to explicitly exclude the _id in the projection.**