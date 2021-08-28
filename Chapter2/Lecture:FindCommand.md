# Lecture: Find command

- In this lesson we used the following commands:

Connect to the Atlas cluster:

```bat
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```
```console
show dbs

use sample_training

show collections

db.zips.find({"state": "NY"})
```
- it iterates through the cursor.

```console
db.zips.find({"state": "NY"}).count()

db.zips.find({"state": "NY", "city": "ALBANY"})

db.zips.find({"state": "NY", "city": "ALBANY"}).pretty()
```

