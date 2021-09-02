*This lesson used the following commands:*

- Connect to the Atlas cluster:
```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

- Switch to this database:
```bash
use sample_training
```

- Find all documents where the trip started and ended at the same station:
```bash
db.trips.find({ "$expr": { "$eq": [ "$end station id", "$start station id"] }
              }).count()
```              

- Find all documents where the trip lasted longer than 1200 seconds, and started and ended at the same station:
```bash
db.trips.find({ "$expr": { "$and": [ { "$gt": [ "$tripduration", 1200 ]},
                         { "$eq": [ "$end station id", "$start station id" ]}
                       ]}}).count()
```