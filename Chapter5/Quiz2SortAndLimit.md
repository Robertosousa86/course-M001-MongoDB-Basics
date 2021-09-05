# Quiz 2: sort() and limit()

## Problem:
- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.
- In what year was the youngest bike rider from the sample_training.trips collection born?

## Answer

**1999**

**To get this result you need to run the following query. The most important part is to first filter out all empty string values, in order to get actual year values. You don't have to use projection here, but we added it so that it is easier to see the answer. The sort order should be in decreasing order because we're looking for the youngest person, therefore the highest year value. You don't have to add the limit() method to get this result, but we also added it to make it easier to immediately see the result.
```bash
db.trips.find({ "birth year": { "$ne":"" } },
              { "birth year": 1 }).sort({ "birth year": -1 }).limit(1)
```              