**Commands used in this lesson:**

- Connect to the Atlas cluster:
```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

- Switch to this database:
```bash
use sample_airbnb
```

- Find all documents with exactly 20 amenities which include all the amenities listed in the query array, and display their price and address:
```bash
db.listingsAndReviews.find({ "amenities":
        { "$size": 20, "$all": [ "Internet", "Wifi",  "Kitchen", "Heating",
                                 "Family/kid friendly", "Washer", "Dryer",
                                 "Essentials", "Shampoo", "Hangers",
                                 "Hair dryer", "Iron",
                                 "Laptop friendly workspace" ] } },
                            {"price": 1, "address": 1}).pretty()
```

- Find all documents that have Wifi as one of the amenities only include price and address in the resulting cursor:
```bash
db.listingsAndReviews.find({ "amenities": "Wifi" },
                           { "price": 1, "address": 1, "_id": 0 }).pretty()
```

- Find all documents that have Wifi as one of the amenities only include price and address in the resulting cursor, also exclude ```"maximum_nights"```. **This will be an error:*
```bash
db.listingsAndReviews.find({ "amenities": "Wifi" },
                           { "price": 1, "address": 1,
                             "_id": 0, "maximum_nights":0 }).pretty()
```                             

- Switch to this database:
```bash
use sample_training
```

- Get one document from the collection:
```bash
db.grades.findOne()
```

- Find all documents where the student in class 431 received a grade higher than 85 for any type of assignment:
```bash
db.grades.find({ "class_id": 431 },
               { "scores": { "$elemMatch": { "score": { "$gt": 85 } } }
             }).pretty()
```

- Find all documents where the student had an extra credit score:
```bash
db.grades.find({ "scores": { "$elemMatch": { "type": "extra credit" } }
               }).pretty()
```               