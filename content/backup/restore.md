---
title: Restore
pcx-content-type: concept
weight: 2
layout: list
meta:
  title: Restore
---

# Restore

We can use mongorestore to restore the whole database.

**_WARNING:_** make sure your new database is empty before restoring!

```bash
mongorestore -d=metahkg --uri=mongodb://<username>:<password>@localhost:<port>
```
