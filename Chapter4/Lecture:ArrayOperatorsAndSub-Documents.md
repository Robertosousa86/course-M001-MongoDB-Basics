**To learn more about querying arrays using MQL visit our excellent documentation page. To learn more about the ```$regex``` operator check out this documentation page.**

- Commands used in this lesson:

- Connect to the Atlas cluster:
```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

```bash
use sample_training
```

```bash
db.trips.findOne({ "start station location.type": "Point" })
```

```bash
db.companies.find({ "relationships.0.person.last_name": "Zuckerberg" },
                  { "name": 1 }).pretty()
```

```bash
db.companies.find({ "relationships.0.person.first_name": "Mark",
                    "relationships.0.title": { "$regex": "CEO" } },
                  { "name": 1 }).count()
```

```bash
db.companies.find({ "relationships.0.person.first_name": "Mark",
                    "relationships.0.title": {"$regex": "CEO" } },
                  { "name": 1 }).pretty()
```

```bash
db.companies.find({ "relationships":
                      { "$elemMatch": { "is_past": true,
                                        "person.first_name": "Mark" } } },
                  { "name": 1 }).pretty()
```

```bash
db.companies.find({ "relationships":
                      { "$elemMatch": { "is_past": true,
                                        "person.first_name": "Mark" } } },
                  { "name": 1 }).count()
```