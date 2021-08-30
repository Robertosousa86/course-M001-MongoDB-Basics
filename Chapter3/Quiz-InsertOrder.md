# Quiz: Insert Order

## Answer

```bash
db.pets.insert([{ "pet": "cat" }, { "pet": "dog" }, { "pet": "fish" }])
```
**_The _id field is not specified in any of these documents, which means that it will be created for each automatically, and it will be unique._**

```bash
db.pets.insert([{ "_id": 1, "pet": "cat" },
                { "_id": 1, "pet": "dog" },
                { "_id": 3, "pet": "fish" },
                { "_id": 4, "pet": "snake" }], { "ordered": false })
```
**_This insert is unordered, which means that each document with a unique _id value will get inserted into the collection, which would make a total of 3 inserted documents._**

```bash
db.pets.insert([{ "_id": 1, "pet": "cat" },
                { "_id": 2, "pet": "dog" },
                { "_id": 3, "pet": "fish" },
                { "_id": 3, "pet": "snake" })
```

**_While there is a duplicate key error between the "fish" and "snake" documents, it occurs at the very end of the insert operation, because this insert is ordered by default. As a result the first 3 documents will get inserted and the last one will create a duplicate key error._**