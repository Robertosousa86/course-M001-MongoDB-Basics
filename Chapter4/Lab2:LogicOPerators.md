# Lab 2: Logic operators

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- How many companies in the sample_training.companies dataset were

- either founded in 2004

[and] either have the social category_code [or] web category_code,
[or] were founded in the month of October

[and] also either have the social category_code [or] web category_code?
Copy/paste the exact numeric value (without double quotes) of the result that you get into the response field.

## Answer

**149**

- To get this value use the following query:

```bash
db.companies.find({ "$and": [
                        { "$or": [ { "founded_year": 2004 },
                                   { "founded_month": 10 } ] },
                        { "$or": [ { "category_code": "web" },
                                   { "category_code": "social" }]}]}).count()
```

**In this case, you have to use an explicit $and. There are two or statements, and to get all the companies that match the required specification both or statements have to be true at the same time.**