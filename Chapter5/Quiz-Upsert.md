# Quiz: Upsert

## Problem:
- How does the upsert option work?


## Answer

- By default upsert is set to false.
**If the upsert option is not specified, then it will have the value of false by default.**

- When upsert is set to true and the query predicate returns an empty cursor, the update operation creates a new document using the directive from the query predicate and the update predicate.
**When upsert is set to true it can perform an insert if the query predicate doesn't return a matching document.**

- When upsert is set to false and the query predicate returns an empty cursor then there will be no updated documents as a result of this operation.
**When upsert is set to false an update will happen only when the query predicate is matched with a document from the collection.**