# Quiz 2: Logic operators

## Problem:
- Which is the most succinct query to return all documents from the sample_training.inspections collection where the inspection date is either "Feb 20 2015", or "Feb 21 2015" and the company is not part of the "Cigarette Retail Dealer - 127" sector?

## Answer

```bash
db.inspections.find(
  { "$or": [ { "date": "Feb 20 2015" },
             { "date": "Feb 21 2015" } ],
    "sector": { "$ne": "Cigarette Retail Dealer - 127" }}).pretty()
```

**This query accounts for both dates that we are looking for and excludes all documents where the sector is "Cigarette Retail Dealer - 127" by using the $ne not equal comparison operator.**