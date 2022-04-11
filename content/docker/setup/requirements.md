---
title: Requirements
pcx-content-type: concept
layout: list
weight: 1
meta:
  title: Requirements
---

# Requirements

## Local

### Git

```bash
$ sudo apt install git
# ubuntu

$ sudo pacman -Sy git
# arch
```

### Docker & docker-compose

```bash
$ sudo apt install docker.io docker-compose
# ubuntu

$ sudo pacman -Sy docker docker-compose 
# arch
```

### Nginx

```bash
$ sudo apt install nginx
# ubuntu

$ sudo pacman -Sy nginx
# arch
```

### Mongodb shell and database tools

- ubuntu (20.04):

```bash
$ sudo apt install gnupg
# install gnupg

$ wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
# import public key

$ echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
# add mongodb apt repositories

$ sudo apt update
# update packages list

$ sudo apt install mongodb-org-shell mongodb-org-tools
# install mongosh and mongodb database tools
```

- arch:

Install from [aur](https://aur.archlinux.org/).

```bash
$ cd ~/Downloads
# go to downloads folder (or any other folders)

$ git clone https://aur.archlinux.org/mongosh-bin.git
$ git clone https://aur.archlinux.org/mongodb-tools-bin.git
# clone the aur repositories

$ cd mongosh-bin
$ makepkg -si
# install mongosh

$ cd ../mongodb-tool-bin
$ makepkg -si
# install mongodb tools

$ cd ..
$ rm -rf mongodb-tools-bin mongosh-bin
# remove the repositories after installation
```

## Third party services

- mailgun (for sending emails) - obtain an api key at [mailgun.com](https://mailgun.com)
- recaptcha - obtain a site key and secret pair from [developers.google.com/recaptcha](https://developers.google.com/recaptcha)

## Domain

A domain (or subdomain) is necessary for a trusted https connection:

- [cloudflare](https://developers.cloudflare.com/registrar/get-started/register-domain/)
- [namecheap](https://www.namecheap.com/)
- You can get a [free domain](https://nc.me/) from namecheap if you are a student

### Deploying locally

If you are deploying locally only, you can use a domain that resolves to localhost
( e.g. `metahkg.test.wcyat.me` )

Or, alternatively, configure the domain to resolve to localhost on your machine only:

```bash
sudo nano /etc/hosts
```

Add a line at the end of /etc/hosts.

```bash
# /etc/hosts

# ...

127.0.0.1 example.com
```
