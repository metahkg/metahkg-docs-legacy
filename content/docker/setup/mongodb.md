---
title: Setup mongodb
pcx-content-type: concept
layout: list
weight: 4
meta:
  title: Setup mongodb
---

# Setup mongodb

Assuming you configured mongodb to run on port 30000.

## Start mongodb

You must start mongodb before following the steps.

```bash
$ cd docker
# switch to the docker directory

$ docker-compose up mongo -d --build
# start mongodb
```

## Configure the databases

`<username>` and `<password>` must be the same `username` and `password` you configured in [Environmental variables](../env).

### Script

Create a .env file at the root of the repository.

```bash
# .env
DB_URI=mongodb://<username>:<password>@localhost:30000
```

Run:

```bash
$ yarn run setup
# or npm run setup
```

### Manually

```bash
$ mongoimport --uri=mongodb://<username>:<password>@localhost:30000 -d=metahkg metahkg-server/templates/server/category.json
# import categories

$ mongosh mongodb://<username>:<password>@localhost:30000
# log into mongodb
```

```javascript
test> use metahkg
// switch to metahkg

metahkg> db.viral.createIndex({ "createdAt": 1 }, { expireAfterSeconds: 172800 })
// expire viral collections after two days
metahkg> db.summary.createIndex({ "op": "text", "title": "text" }) 
// for text search
metahkg> db.limit.createIndex({ "createdAt": 1 }, { expireAfterSeconds: 86400 })
// expire limit collections after a day
metahkg> db.verification.createIndex({ "createdAt": 1 }, { expireAfterSeconds: 604800 })
// expire verification collections after 7 days
metahkg> exit
```
