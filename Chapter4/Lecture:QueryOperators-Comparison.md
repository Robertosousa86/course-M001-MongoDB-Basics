# Citi Bike Historical data

*This lesson used the following commands:*

- Connect to the Atlas cluster:

```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

- Switch to this database:
```bash
use sample_training
```

- Find all documents where the tripduration was less than or equal to 70 seconds and the usertype was not Subscriber:
```bash
db.trips.find({ "tripduration": { "$lte" : 70 },
                "usertype": { "$ne": "Subscriber" } }).pretty()
```

- Find all documents where the tripduration was less than or equal to 70 seconds and the usertype was Customer using a redundant equality operator:
```bash
db.trips.find({ "tripduration": { "$lte" : 70 },
                "usertype": { "$eq": "Customer" }}).pretty()
```

- Find all documents where the tripduration was less than or equal to 70 seconds and the usertype was Customer using the implicit equality operator:
```bah
db.trips.find({ "tripduration": { "$lte" : 70 },
                "usertype": "Customer" }).pretty()
```