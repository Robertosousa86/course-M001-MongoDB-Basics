# Quiz: Object Id

## Problem
- How does the value of _id get assigned to a document?

## Answer

**_It is automatically generated as an ObjectId type value._**

When inserting a document via the Data Explorer in Atlas, the _id value is already generated as an ObjectID type, while the rest of the fields are not.

**_You can select a non ObjectId type value when inserting a new document, as long as that value is unique to this document._**

MongoDB generates a value, so that there is one just in case. You can definitely change the default value to a different value or data type, as long as they are unique to this document and not an array.

