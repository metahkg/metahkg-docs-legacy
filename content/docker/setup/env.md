---
title: Environmental variables
pcx-content-type: concept
layout: list
weight: 3
meta:
  title: Environmental variables
---

# Environmental variables

## Copy environment variables

```bash
cd docker
cp temp.env .env
```

## Edit varibles in .env according to the descriptions

```bash
# .env

port=3000
# port for the whole app

MONGO_PORT=30000
# mongodb port

MONGO_USER=username 
# mongodb username

MONGO_PASSWORD=password 
# mongodb password

mailgun_key=<mailgun-api-key>
# mailgun api key: obtain one at https://mailgun.com, 
# the flex plan is free (with a limit of about 7000 emails)

domain=metahkg.org
# please change to your domain name

REACT_APP_recaptchasitekey=<recaptcha-site-key>
# recaptcha site key, must be a pair with recaptcha secret

recaptchasecret=<recaptcha-secret>
# recatcha secret, must be a pair with recaptcha site key

jwtKey=<your-jwt-key>
# jwt key is used to sign jwts (jsonwebtoken), please use a strong value

DOCKER_PREFIX=
# configure this if you want to use a prefix for the docker container names
# e.g. when you need to deploy more than a instance of metahkg
```
