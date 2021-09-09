# Lecture: Atlas feature-More data explorer

## Get Started with Atlas Search

**IMPORTANT**

- Serverless Instances are in Preview
- Serverless instances are in preview and do not support this feature at this time. To learn more, see Serverless Instance Limitations.

**_This tutorial takes you through the steps of setting up and querying an Atlas Search index. You will use a collection with movie data from the Atlas sample data set._**

```
Prerequisites
NOTE
Atlas Search is available on all cluster tiers running MongoDB version 4.2 or later.
```

- To complete this tutorial you will need:

An Atlas cluster with MongoDB version 4.2 or higher.
The sample datasets loaded into your Atlas cluster.
mongosh on your local machine.
You must have the:

Project Data Access Read Only or higher role to view Atlas Search analyzers and indexes using the Atlas UI or API.
Project Data Access Admin or higher role to create and manage Atlas Search analyzers and indexes using the Atlas UI or API.
You must meet the following additional prerequisites if you want to create an Atlas Search index using the Atlas Search API:

Have an API Key assigned the Project Data Access Admin or Project Owner role for your Atlas project. An API Key consists of a public and private key pair.

***TIP***
Users with the Project Owner role can create and assign project access to API Keys.

Send the request from a client that appears in the access list for your API Key.

TIP
Users with the Organization Owner role can create access list entries for your API Key.
```
