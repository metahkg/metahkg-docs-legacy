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
# port that the whole thing runs on

MONGO_PORT=30000
# mongodb port

MONGO_USER=username
# mongodb username

MONGO_PASSWORD=password
# mongodb password

domain=metahkg.org
# please change to your domain name

mailgun_key=<mailgun-api-key>
# mailgun api key: obtain one at https://mailgun.com,
# the flex plan is free (with a limit of about 7000 emails)

mailgun_domain=
# mailgun domain, if different from the domain

LINKS_DOMAIN=l.metahkg.org
# metahkg links domain

signupmode=normal
# "normal" | "invite" | "none"
# https://docs.metahkg.org/customize/signupmode/

REACT_APP_recaptchasitekey=<recaptcha-site-key>
# recaptcha site key, must be a pair with recaptcha secret

recaptchasecret=<recaptcha-secret>
# recatcha secret, must be a pair with recaptcha site key

jwtKey=<your-jwt-key>
# used to sign jwts, plese use a strong one

COMPOSE_PROJECT_NAME=
# configure this for different container names (so you can run multiple instances of metahkg)

cors=
# give some value (e.g. true) to this to support cors

env=
# set this to dev to enable hot reload

branch=master
# select a branch (dev/master) for prebuilt images. If you use the normal build from source, ignore this.
```
