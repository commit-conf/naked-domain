# TL;DR

The purpose of this project is to redirect the naked domain (with 302, here is the problem) `http(s)://commit-conf.com` to `https://<edition>.commit-conf.com`

# Developing

Edit `firebase.json` to change the redirect

# To deploy

```
firebase --project "commit-conf" deploy
```

# Configuration

```
npm install -g firebase-tools

firebase login

mkdir website
```

# The long story

GitHub only supports custom domains for naked domains (and www) OR a subdomain. We cannot use both. So we are using Firebase Hosting to redirect from naked domain to the last edition subdomain. But if we use the current hosting dashboard, and we try to config the redirection there, it will configure a 301 redirect (and the browsers will cache it). So we are doing the redirection with the firebase.json config file. The other option was using Cloudflare as a proxy or managing our own server.
