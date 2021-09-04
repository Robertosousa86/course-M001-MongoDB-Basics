# Quiz: Aggregation framework

## Problem:
- What are the differences between using aggregate() and find()?

## Answer

- ```aggregate()``` can do what find() can and more.

**Any find() query can be translated into an aggregation pipeline equivalent, but not every aggregation pipeline can be translated into a find() query.**

- ```aggregate()``` allows us to compute and reshape data in the cursor.

**The aggregation framework allows us to compute and reshape data via using stages like $group, $sum, and others.**
