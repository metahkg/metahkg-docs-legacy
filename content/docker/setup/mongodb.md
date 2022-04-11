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

$ docker-compose up mongo --build
# start mongodb
```

## Setup

### Create user

You have the root privileges in the admin database, but have no rights in other databases.
You must create a user in the databases to do read and write operations.

`<username>` and `<password>` must be the same `username` and `password` you configured in [Environmental variables](../env).

```bash
$ mongosh mongodb://<username>:<password>@localhost:30000
# log into mongodb

test> use metahkg-threads
# switch to metahkg-threads
metahkg-threads> db.createUser({ user: "<username>", pwd: "<password>", roles: [ { role: "readWrite", db: "metahkg-threads" } ] })
# create a user at metahkg-threads
metahkg-threads> use metahkg-users
# switch to metahkg-users
metahkg-users> db.createUser({ user: "<username>", pwd: "<password>", roles: [ { role: "readWrite", db: "metahkg-users" } ] })
# create a user at metahkg-users
metahkg-users> exit
```

### Configure the databases

`<username>` and `<password>` must be the same `username` and `password` you configured in [Environmental variables](../env).

```bash
$ mongoimport --uri=mongodb://<username>:<password>@localhost:30000 -d=metahkg-threads metahkg-server/templates/server/category.json
# import categories

$ mongosh mongodb://<username>:<password>@localhost:30000
# log into mongodb

test> use metahkg-threads
# switch to metahkg-threads

metahkg-threads> db.hottest.createIndex({ "createdAt": 1 }, { expireAfterSeconds: 172800 })
# expire hottest collections after two days
metahkg-threads> db.summary.createIndex({ "op": "text", "title": "text" }) 
# for text search
metahkg-threads> use metahkg-users
# switch to metahkg-users

metahkg-users> db.limit.createIndex({ "createdAt": 1 }, { expireAfterSeconds: 86400 })
# expire limit collections after a day
metahkg-users> db.verification.createIndex({ "createdAt": 1 }, { expireAfterSeconds: 604800 })
# expire verification collections after 7 days
metahkg-users> exit
```
