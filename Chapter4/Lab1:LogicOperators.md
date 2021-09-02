# Lab 1: Logic operators

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- Before solving this exercise, make sure to undo some of the changes that we made to the zips collection earlier in the course by running the following command:

```bash
db.zips.updateMany({ "city": "HUDSON" }, { "$inc": { "pop": -10 } })
```

- How many zips in the sample_training.zips dataset are neither over-populated nor under-populated?

- In this case, we consider population of more than 1,000,000 to be over- populated and less than 5,000 to be under-populated.

- Copy/paste the exact numeric value (without double quotes) of the result that you get into the response field.

## Answer

**11193**

- To get this value use the following range query:

```bash
db.zips.find({ "pop": { "$gt": 5000, "$lt": 1000000 }}).count()
```

- You could also use the $nor operator if you want to use a logic operator like so:

```bash
db.zips.find({ "$nor": [ { "pop": { "$lt":5000 } },
             { "pop": { "$gt": 1000000 } } ] } ).count()
```

**The best operator for this case is $nor, it excludes both cases from consideration and we are left with the**
