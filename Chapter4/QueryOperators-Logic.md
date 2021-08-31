# Logical Query Operators Documentation

- This lesson used the following commands:

- Connect to the Atlas cluster:
```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

- Switch to this database:
```
use sample_training
```

- Find all documents where airplanes CR2 or A81 left or landed in the KZN airport:
```bash
db.routes.find({ "$and": [ { "$or" :[ { "dst_airport": "KZN" },
                                    { "src_airport": "KZN" }
                                  ] },
                          { "$or" :[ { "airplane": "CR2" },
                                     { "airplane": "A81" } ] }
                         ]}).pretty()
```