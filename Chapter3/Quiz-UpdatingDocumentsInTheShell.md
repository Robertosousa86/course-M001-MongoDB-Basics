# Quiz: Updating Documents in the shell

## Problem
- Given a pets collection where each document has the following structure and fields:

## Answer

```bash
db.pets.updateMany({ "pet": "cat" },
                   { "$set": { "type": "dangerous",
                               "look": "adorable" }})
```

**_Fields "type" and "look" do not exist in the existing documents in the collection, so this command will create new fields with the given values for all documents that have the "pet" field equal to "cat"._**

```bash
db.pets.updateMany({ "pet": "cat" },
                   { "$push": { "climate": "continental",
                                "look": "adorable" } })
```

**_While the "climate" field is already present in the documents in this collection, the field "look" is new, and this command will create a new array field called "look", with one element "adorable" in it._**