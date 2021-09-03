# Quiz 2: $expr

## Problem:
- Which of the following statements will find all the companies that have more employees than the year in which they were founded?

## Answer

```bash
db.companies.find(
  { "$expr": { "$gt": [ "$number_of_employees", "$founded_year" ] }}).count()
```

We have to use the $expr operator to compare the two field values within each document. Using the $expr operator is the reason why we have to use the aggregation syntax for the comparison operator.

 COPY
db.companies.find(
  { "$expr": { "$lt": [ "$founded_year", "$number_of_employees" ]}}).count()
This is correct.

When we swap the compared fields and use the $lt less than operator instead of the $gt greater than operator, the result should still be correct.
