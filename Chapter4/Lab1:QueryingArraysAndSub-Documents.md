# Lab 1: Querying arrays and sub-documents

## Problem:

- To complete this exercise connect to your Atlas cluster using the in-browser IDE space at the end of this chapter.

- How many trips in the sample_training.trips collection started at stations that are to the west of the -74 longitude coordinate?

- Longitude decreases in value as you move west.

- Note: We always list the longitude first and then latitude in the coordinate pairs; i.e.

<field_name>: [ <longitude>, <latitude> ]

## Answer

**1928**

- To get this value use the following query:

```bash
db.trips.find({ "start station location.coordinates.0": { "$lt": -74 }}).count()
```

**The _"start station location"_ has a sub-document that contains the coordinates array. To get to this coordinates array we must use use dot-notation. We can issue a range query to find all documents in this longitude. The caveat is to remember that all trips take place in NYC so the latitude value in the coordinates array will always be positive, and we don't have to worry about it when issuing a range query like this.**