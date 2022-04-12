---
title: Remove Category
pcx-content-type: concept
weight: 4
layout: list
meta:
  title: Remove Category
---

# Remove Category

## Log into mongodb

```bash
mongosh mongodb://<username>:<password>@localhost:30000/metahkg
```

## List the categories

```javascript
metahkg> db.category.find().pretty()
```

Find the id of the one you want to remove.

## Caution

Please, DO NOT remove category 1 ({ id: 1 }), or the output might not be as expected.

## Remove

```javascript
metahkg> db.category.deleteOne({ id: <id> })
```
