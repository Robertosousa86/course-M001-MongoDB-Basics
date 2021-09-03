# Lab 1: Array operators

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- What is the name of the listing in the sample_airbnb.listingsAndReviews dataset that accommodates more than 6 people and has exactly 50 reviews?

- Copy/Paste the value of the "name" field into the response field without quotation marks.

## Answer

**Sunset Beach Lodge Retreat**

- To get this value use the following query:
```bash
db.listingsAndReviews.find({ "reviews": { "$size":50 },
                             "accommodates": { "$gt":6 }})
```                             
- We can use the $size operator to select only the documents that have exactly 50 elements in the reviews field. This query can also run in Atlas so that it is easier to see the value of the name field right away.