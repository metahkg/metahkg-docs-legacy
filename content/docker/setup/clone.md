---
title: Cloning the repositories
pcx-content-type: concept
layout: list
weight: 1
meta:
  title: Cloning the repositories
---

# Clone the repositories

```bash
$ git clone --recursive-submodules https://gitlab.com/metahkg/metahkg.git
# you must clone the submodules

$ cd metahkg

$ git checkout dev # only dev branch supports docker as of 10/04/22

$ git submodule foreach git pull # update the repositories
```
