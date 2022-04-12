---
title: Sign up mode
pcx-content-type: concept
weight: 2
layout: list
meta:
  title: Sign up mode
---

# Sign up mode

You can set up sign up mode to restrict the sign up of users.

## Modes

### Normal

Anyone with a email can sign up.

### Invite

!!! Frontend not implemented !!!
Anyone with an invite code can sign up.

To add invite codes:

```javascript
metahkg> db.invite.insertOne({ code: "<code>" })
```

### None

No one can sign up.

## Configure sign up mode

### Docker

```bash
nano docker/.env
```

```bash
# docker/.env

# ...

# find the line `signupmode`

signupmode=<mode>
```

### Metahkg-server

```bash
nano metahkg-server/.env
```

```bash
# metahkg-server/.env

# ...

# find the line `signupmode`

signupmode=<mode>
```
