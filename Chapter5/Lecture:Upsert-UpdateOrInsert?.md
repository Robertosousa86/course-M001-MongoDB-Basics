# Lecture: Upsert - Update or Insert?

 ***Obs***: 
**Upsert is  a hybrid of update and insert, it should only be used when it is needed**

- Commands used in this lesson:

````bash
db.iot.updateOne({ "sensor": r.sensor, "date": r.date,
                   "valcount": { "$lt": 48 } },
                         { "$push": { "readings": { "v": r.value, "t": r.time } },
                        "$inc": { "valcount": 1, "total": r.value } },
                 { "upsert": true }
````
