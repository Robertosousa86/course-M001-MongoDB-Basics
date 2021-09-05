# Quiz 1: Sort() and Limit()

## Problem:
- Which of the following commands will return the name and founding year for the 5 oldest companies in the sample_training.companies collection?

## Answer

```bash
db.companies.find({ "founded_year": { "$ne": null }},
                  { "name": 1, "founded_year": 1 }
                 ).sort({ "founded_year": 1 }).limit(5)
```
**We first must filter out the documents where the founded year is not null, then project the fields that we are looking for, which is name, and founded_year in this case. Then we sort the cursor in increasing order, so the first results will have the smallest value for the founded_year field. Finally, we limit the results to our top 5 documents in the cursor, thus getting the 5 oldest companies in this collection.**

```bash
db.companies.find({ "founded_year": { "$ne": null }},
                  { "name": 1, "founded_year": 1 }
                 ).limit(5).sort({ "founded_year": 1 })
```
**While the limit() and sort() methods are not listed in the correct order, MongoDB flips their order when executing the query, delivering the results that the question prompt is looking for.**