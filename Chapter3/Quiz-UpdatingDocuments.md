# Quiz: Updating documents

## Problem:
- MongoDB has a flexible data model, which means that you can have fields that contain documents, or arrays as their values.

## Answer

```bash
{ "_id": 1,
  "pet": "cat",
  "attributes": [ { "coat": "fur",
                    "type": "soft" },
                  { "defense": "claws",
                    "location": "paws",
                    "nickname": "murder mittens" } ],
  "name": "Furball" }
```

```bash
{ "_id": 1,
  "pet": "cat",
  "fur": "soft",
  "claws": "sharp",
  "name": "Furball" }
```

```bash
{ "_id": 1,
  "pet": "cat",
  "attributes": { "coat": "soft fur",
                  "paws": "cute but deadly" },
  "name": "Furball" }
  ```

**None of the above.**
**_All the documents presented in the choices are valid MongoDB documents._**