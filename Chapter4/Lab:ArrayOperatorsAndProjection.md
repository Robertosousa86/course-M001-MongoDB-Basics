# Lab: Array operators and projection

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- How many companies in the sample_training.companies collection have offices in the city of Seattle?

- Copy/paste your answer to the response field.

## Answer

**117**

- To get this value use the following query:
```bash
db.companies.find({ "offices": { "$elemMatch": { "city": "Seattle" } }
                  }).count()
```

**_"offices"_ is an array that contains documents with the address information from each office. We use $elemMatch to return all documents in which an office array element contains the field city with the value Seattle.**