---
title: Insert Category
pcx-content-type: concept
weight: 3
layout: list
meta:
  title: Insert Category
---

# Insert Category

## Log into mongodb

```bash
mongosh mongodb://<username>:<password>@localhost:30000/metahkg
```

## Check for categories

```bash
metahkg> db.category.find().pretty()
```

Use an id that does not exist yet in the next step.

## Insert

```javascript
metahkg> db.category.insertOne({ id: <newid>, name: "<new-category-name>" })
// normal category

metahkg> db.category.insertOne({ id: <newid>, name: "<new-category-name>", hidden: true })
// hidden category
```

Reload the app and you should now see the new category.