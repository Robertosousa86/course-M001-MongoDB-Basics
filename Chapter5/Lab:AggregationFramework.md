# Lab: Aggregation framework

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- What room types are present in the sample_airbnb.listingsAndReviews collection?

## Answer

- **Shared room**

- **Entire home/apt**

- **Private room**

**To get this result you need to run the following query.**

```bash
db.listingsAndReviews.aggregate([ { "$group": { "_id": "$room_type" } }])
```