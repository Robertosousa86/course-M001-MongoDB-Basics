# Introduction to indexes

_To learn more about performance and indexing with MongoDB, take our MongoDB Performance Course!_

- Commands used in this lesson:

```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

```bash
use sample_training

db.trips.find({ "birth year": 1989 })

db.trips.find({ "start station id": 476 }).sort( { "birth year": 1 } )

db.trips.createIndex({ "birth year": 1 })

db.trips.createIndex({ "start station id": 1, "birth year": 1 })
```