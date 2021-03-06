---
title: Cloning the repositories
pcx-content-type: concept
layout: list
weight: 2
meta:
  title: Cloning the repositories
---

## Clone the repositories

```bash
$ git clone --recurse-submodules https://gitlab.com/metahkg/metahkg.git
# you must clone the submodules

$ cd metahkg

$ git checkout dev
# (or master)

$ git submodule foreach git checkout dev
# check out a branch (dev or master)

$ git submodule foreach git pull 
# update the submodules
```

## Pull submodules after clone

If you didn't use the --recurse-submodules flag when cloning, or you need to pull a new submodule, you can do this:

```bash
$ git pull --recurse-submodules
# pull with submodules

$ git submodule checkout dev
# check out a branch (dev or master)

$ git submodule foreach git pull 
# update the submodules
```
