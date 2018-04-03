<p align="center">
  <img height="256" src="https://raw.githubusercontent.com/fs-opensource/hapi-pm2-zero-downtime/master/media/hapi-pm2-zero-downtime.png" alt="hapi-pm2-zero-downtime logo">
</p>

<p align="center">
    <a href="https://travis-ci.org/fs-opensource/hapi-pm2-zero-downtime"><img src="https://camo.githubusercontent.com/9f56ef242c6f588f74f39f0bd61c1acd34d853af/68747470733a2f2f7472617669732d63692e6f72672f66732d6f70656e736f757263652f686170692d67656f2d6c6f636174652e7376673f6272616e63683d6d6173746572" alt="Build Status" data-canonical-src="https://travis-ci.org/fs-opensource/hapi-pm2-zero-downtime.svg?branch=master" style="max-width:100%;"></a>
    <a href="https://snyk.io/test/github/fs-opensource/hapi-pm2-zero-downtime"><img src="https://snyk.io/test/github/fs-opensource/hapi-pm2-zero-downtime/badge.svg" alt="Known Vulnerabilities" data-canonical-src="https://snyk.io/test/github/fs-opensource/hapi-pm2-zero-downtime" style="max-width:100%;"></a>
    <a href="https://www.npmjs.com/package/hapi-pm2-zero-downtime"><img src="https://img.shields.io/npm/v/hapi-pm2-zero-downtime.svg" alt="hapi-pm2-zero-downtime Version" data-canonical-src="https://img.shields.io/npm/v/hapi-pm2-zero-downtime.svg" style="max-width:100%;"></a>
</p>

------

<p align="center"><sup>Development of this hapi plugin is supported by <a href="https://futurestud.io">Future Studio University 🚀</a></sup>
<br><b>
Join the <a href="https://futurestud.io/university">Future Studio University and Skyrocket in Node.js</a></b>
</p>

------


## Introduction
A hapi plugin that gracefully stops the hapi server on `SIGINT`. This is a great combination with **PM2** to accomplish zero-downtime deployments!

This serves existing requests before closing the connection and stopping the hapi server process.

It uses hapi’s `server.stop()` method to close connections properly.


## Requirements
> **hapi v17** and **Node.js v8 (or newer)**

This plugin requires **hapi v17** (or later) and uses async/await which requires **Node.js v8 or newer**.


## Installation
Add `hapi-pm2-zero-downtime` as a dependency to your project:

```bash
# NPM v5 users, this way is yours
npm i hapi-pm2-zero-downtime

# you’re using NPM v4:
npm i -S hapi-pm2-zero-downtime

```


## Usage
**`hapi-pm2-zero-downtime` is enabled by default.**

The most straight forward way to register the `hapi-pm2-zero-downtime` plugin:

```js
await server.register({
  plugin: require('hapi-pm2-zero-downtime'),
  options: {
    // any option that is supported by hapi's "server.stop()", e.g.
    timeout: 15000
  }
})
```


## Plugin Registration Options
`hapi-pm2-zero-downtime` passes the options through to hapi’s [`server.stop(options)`](https://hapijs.com/api#-await-serverstopoptions).
This way, customize the behavior of `server.stop()`, like the `timeout` before forcefully stopping the process.


## Feature Requests
Do you miss a feature? Please don’t hesitate to
[create an issue](https://github.com/fs-opensource/hapi-pm2-zero-downtime/issues) with a short description of your desired addition to this plugin.


## Links & Resources

- [hapi tutorial series](https://futurestud.io/tutorials/hapi-get-your-server-up-and-running) with 80+ tutorials


## Contributing

1.  Create a fork
2.  Create your feature branch: `git checkout -b my-feature`
3.  Commit your changes: `git commit -am 'Add some feature'`
4.  Push to the branch: `git push origin my-new-feature`
5.  Submit a pull request 🚀


## License

MIT © [Future Studio](https://futurestud.io)

---

> [futurestud.io](https://futurestud.io) &nbsp;&middot;&nbsp;
> GitHub [@fs-opensource](https://github.com/fs-opensource/) &nbsp;&middot;&nbsp;
> Twitter [@futurestud_io](https://twitter.com/futurestud_io)
