# Passport-OpenID Connect

[Passport](https://github.com/jaredhanson/passport) strategy for authenticating
with [OpenID Connect](http://openid.net/connect/).

This module lets you authenticate using OpenID Connect in your Node.js
applications.  By plugging into Passport, OpenID Connect authentication can be
easily and unobtrusively integrated into any application or framework that
supports [Connect](http://www.senchalabs.org/connect/)-style middleware,
including [Express](http://expressjs.com/).

**This fork has been created due to unmerged required PRs to support our production use cases:**
* [x] https://github.com/jaredhanson/passport-openidconnect/pull/54

It has been tested with different OpenID Connect providers like [Google](https://accounts.google.com/.well-known/openid-configuration) and [OneLogin](https://www.onelogin.com/) by integration in [Feathers](https://feathersjs.com/) (please read [this article](https://blog.feathersjs.com/how-to-setup-oauth-flow-with-featherjs-522bdecb10a8) for more details).

## Testing during development

Some providers have strict security concerns so that you cannot use `localhost`, non-standard ports or need to enforce HTTPS in redirect URLs. Let's say we have our app running on `localhost:8080` in HTTP or `localhost:8083` in HTTPS and we'd like to test it.

First we create a "fake" domain by editing the `hosts` file (*/etc/hosts* under Linux or *C:\Windows\System32\drivers\etc\hosts* under Windows)  and add this line to redirect it to local host:
```
127.0.0.1 test.airbusoidc.com
```

Then, since the `hosts` file does not allow to manage port redirections we need to do so using the operating system network tools.

### Windows

To see what is currently running:
```
netstat -a -n -p TCP | grep "LISTENING"
```

To add port redirection for HTTP:
```
netsh interface portproxy add v4tov4 listenport=80 listenaddress=127.0.0.1 connectport=8080 connectaddress=127.0.0.1
```

To add port redirection for HTTPS:
```
netsh interface portproxy add v4tov4 listenport=443 listenaddress=127.0.0.1 connectport=8083 connectaddress=127.0.0.1
```

To see running proxied port:
```
netsh interface portproxy show v4tov4
```

To see remove proxied port:
```
netsh interface portproxy delete v4tov4 listenport=80 listenaddress=127.0.0.1
```

### Linux

**TODO**
