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
