# Quiz operators

## Problem:
- Which of the following queries will return all listings that have "Free parking on premises", "Air conditioning", and "Wifi" as part of their amenities, and have at least 2 bedrooms in the sample_airbnb.listingsAndReviews collection?

## Answer
```bash
db.listingsAndReviews.find(
  { "amenities":
     { "$all": [ "Free parking on premises", "Wifi", "Air conditioning" ] },
    "bedrooms": { "$gte":  2 } }).pretty()
```

- We have to use the ```$all``` array operator In order to get all documents where the amenities array contains these three elements regardless of their order. To get the desired number of bedrooms the best operator to use is $gte, since it includes 2, but also shows other listings with more bedrooms.