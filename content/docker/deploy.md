---
title: Deploying Metahkg
pcx-content-type: concept
weight: 2
layout: list
meta:
  title: Deploying Metahkg
---

# Deploying Metahkg

We support:

- building images locally (default)
- using prebuilt images

## Build locally

```bash
$ yarn docker
# build and start the containers
```

## Using prebuilt images

**_WARNING:_** The images are built on gitlab ci/cd and are pushed a few minutes after each commit. If you find the api and web app incompatible, try to redeploy a few minutes later.

**_NOTE:_** The images follow a rolling release (new images are built every commit), so there's is ONLY ONE TAG (latest).

**_NOTE:_** The nginx container is still built locally since it is just some copying of files.

You can use prebuilt images so you don't need to waste hardware building (given that your machine might crash due to high memory usage).

### Environment

Please add `branch=master` or `branch=dev` to docker/.env if you haven't to configure which branch of images you would like to use.

### Start

```bash
$ yarn docker:prebuilt
# pull the docker images and deploy
```

## Metahkg is now deployed locally

Metahkg is at localhost:3000 (if you didn't alter the port). To enable metahkg links and/or make your instance public, please [configure nginx](../nginx).
