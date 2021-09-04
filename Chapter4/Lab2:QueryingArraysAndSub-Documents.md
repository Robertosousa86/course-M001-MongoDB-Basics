# Lab 2: Querying arrays and sub-documents

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- How many inspections from the sample_training.inspections collection were conducted in the city of NEW YORK?

## Answer

**18279**

- To get this value use the following query:

```bash
db.inspections.find({ "address.city": "NEW YORK" }).count()
```

**Here we need to use dot-notation to get to the "city" field and search for all documents where this field is equal to "NEW YORK".**