# Quiz: Querying arrays and sub-documents

## Problem:
- Which of the following queries will return the names and addresses of all listings from the sample_airbnb.listingsAndReviews collection where the first amenity in the list is "Internet"?

## Answer

```bash
db.listingsAndReviews.find({ "amenities.0": "Internet" },
                           { "name": 1, "address": 1 }).pretty()
```

**To reach the first element in an array field we need to use dot notation and the element's position which is zero for the first element in most arrays in most languages. For the projection part, we don't need to explicitly exclude the _id field because the question prompt isn't terribly strict about that.**