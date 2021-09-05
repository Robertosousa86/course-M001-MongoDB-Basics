# Lecture: Sort() and Limit()

- There is another fun method called skip() that might come in handy with sort() and limit(). Read more about it on the documentation page.

- Commands used in this lesson:

- Connect to the Atlas cluster:
```bash
mongo "mongodb+srv://<username>:<password>@<cluster>.mongodb.net/admin"
```

```bash
use sample_training
```

```bah
db.zips.find().sort({ "pop": 1 }).limit(1)
```

```bash
db.zips.find({ "pop": 0 }).count()
```

```bash
db.zips.find().sort({ "pop": -1 }).limit(1)
```

```bash
db.zips.find().sort({ "pop": -1 }).limit(10)
```

```bash
db.zips.find().sort({ "pop": 1, "city": -1 })
```