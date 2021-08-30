In this lesson we used the following commands:

```bash
mongoimport --uri="mongodb+srv://<username>:<password>@<cluster>.mongodb.net/sample_supplies" sales.json
```
- Step one: Connect to the Atlas cluster
```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

- Step two: navigate to the database that we need:
```bash
use sample_training
```

- Step three, get a random document from the collection:
```bash
db.inspections.findOne();
```

- Step four, copy this random document, and try to insert in into the collection:
```bash
db.inspections.insert({
      "_id" : ObjectId("56d61033a378eccde8a8354f"),
      "id" : "10021-2015-ENFO",
      "certificate_number" : 9278806,
      "business_name" : "ATLIXCO DELI GROCERY INC.",
      "date" : "Feb 20 2015",
      "result" : "No Violation Issued",
      "sector" : "Cigarette Retail Dealer - 127",
      "address" : {
              "city" : "RIDGEWOOD",
              "zip" : 11385,
              "street" : "MENAHAN ST",
              "number" : 1712
         }
  })
```

```bash
db.inspections.insert({
      "id" : "10021-2015-ENFO",
      "certificate_number" : 9278806,
      "business_name" : "ATLIXCO DELI GROCERY INC.",
      "date" : "Feb 20 2015",
      "result" : "No Violation Issued",
      "sector" : "Cigarette Retail Dealer - 127",
      "address" : {
              "city" : "RIDGEWOOD",
              "zip" : 11385,
              "street" : "MENAHAN ST",
              "number" : 1712
         }
  })
```

```bash
db.inspections.find({"id" : "10021-2015-ENFO", "certificate_number" : 9278806}).pretty()
```