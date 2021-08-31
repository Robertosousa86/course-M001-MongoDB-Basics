# Lab 3: Comparison Operators

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- Using the sample_training.routes collection find out which of the following statements will return all routes that have at least one stop in them?

## Answer
```bash
db.routes.find({ "stops": { "$gt": 0 }}).pretty()
```
**The given query looks for strict equality where the stops field has to be greater than zero, thus excluding all zero stops.**

```bash
db.routes.find({ "stops": { "$ne": 0 }}).pretty()
```
**This query will also work, given that there are no non-negative or non- numeric values in this collection. It returns all documents where the stops field is not equal to 0.**
