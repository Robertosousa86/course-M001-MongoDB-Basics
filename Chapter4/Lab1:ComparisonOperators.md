# Lab 1: Comparison operators

## Problems
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- How many documents in the sample_training.zips collection have fewer than 1000 people listed in the pop field?

- Copy/paste the exact numeric value (without double quotes) of the result that you get into the response field.

## Answer

**8065**

To get this value use the following query:
```bash
db.zips.find({ "pop": { "$lt": 1000 }}).count()
```
Use the $lt instead of $lte operator to exclude all documents that have exactly 1000 people listed in the pop field.