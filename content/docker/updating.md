---
title: Updating
pcx-content-type: concept
weight: 4
layout: list
meta:
  title: Updating
---

# Updating to a newer commit

You should check for updates regularly.

## Pull the repositories

```bash
$ git pull origin dev 
# or master depending on your current branch

$ git submodule foreach git pull
# pull the submodules
```

## Rebuild docker

```bash
$ cd docker
# switch to docker folder

$ docker-compose up -d --build
# build and start the containers

$ yarn run clean:docker
# remove unused images (encountering an error is fine)
```
