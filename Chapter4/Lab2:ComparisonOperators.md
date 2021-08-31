# Lab 2: Comparison operators

## Problem
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- What is the difference between the number of people born in 1998 and the number of people born after 1998 in the sample_training.trips collection?

- Enter the exact numeric value of the result that you get into the response field.

## Answer
**6**

You can use the following queries to get this value:
```bash
db.trips.find({ "birth year": { "$gt": 1998 }}).count()
db.trips.find({ "birth year": 1998 }).count()
```
Use the $gt instead of $gte operator to exclude all 1998 births, and then see how many people were born in 1998 by using implicit equality, then subtract the two values to get the difference.