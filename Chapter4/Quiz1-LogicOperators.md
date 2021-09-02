# Quiz 1: Logic operators

## Problem
- Problem:

- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- How many businesses in the sample_training.inspections dataset have the inspection result "Out of Business" and belong to the "Home Improvement Contractor - 100" sector?

- Enter the exact numeric value of the result that you get into the response field.

## Answer
**4**

- To get this value use the following query:
```bash
db.inspections.find({ "result": "Out of Business",
                      "sector": "Home Improvement Contractor - 100" }).count()
```

**This is a trick question because there is no need to explicitly use a logic operator, you can get the result by using an implicit $and and specifying the query conditions separated by a comma. However, you will still get the right answer if you used an explicit $and operator to reach this answer.**