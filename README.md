![Async Logo](https://raw.githubusercontent.com/caolan/async/master/logo/async-logo_readme.jpg)

[![Build Status via Travis CI](https://travis-ci.org/caolan/async.svg?branch=master)](https://travis-ci.org/caolan/async)
[![Build Status via Azure Pipelines](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)
[![NPM version](https://img.shields.io/npm/v/async.svg)](https://www.npmjs.com/package/async)
[![Coverage Status](https://coveralls.io/repos/caolan/async/badge.svg?branch=master)](https://coveralls.io/r/caolan/async?branch=master)
[![Join the chat at https://gitter.im/caolan/async](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/async?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/async/badge?style=rounded)](https://www.jsdelivr.com/package/npm/async)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [asynchronous JavaScript](http://caolan.github.io/async/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i async`, it can also be used directly in the browser.  A ESM/MJS version is included in the main `async` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`async-es`](https://www.npmjs.com/package/async-es).

For Documentation, visit <https://caolan.github.io/async/>

*For Async v1.5.x documentation, go [HERE](https://github.com/caolan/async/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var async = require("async");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

async.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var async = require("async");

// ...or ES2017 async functions
async.mapLimit(urls, 5, async function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```

Auto-commit on 2025-02-24 19:29:14 | rand=75396

Auto-commit on 2025-02-24 19:41:13 | rand=77702

Auto-commit on 2025-02-24 19:53:18 | rand=26270

Auto-commit on 2025-02-24 20:05:24 | rand=32236

Auto-commit on 2025-02-24 20:17:27 | rand=76153

Auto-commit on 2025-02-24 20:29:27 | rand=29667

Auto-commit on 2025-02-24 20:41:32 | rand=78401

Auto-commit on 2025-02-25 12:10:36 | rand=73357

Auto-commit on 2025-02-25 12:15:16 | rand=3119

Auto-commit on 2025-02-25 12:27:14 | rand=76683

Auto-commit on 2025-02-25 12:39:23 | rand=10510

Auto-commit on 2025-02-25 12:51:25 | rand=16788

Auto-commit on 2025-02-25 13:03:27 | rand=2736

Auto-commit on 2025-02-25 13:15:34 | rand=86358

Auto-commit on 2025-02-25 13:27:42 | rand=21837

Auto-commit on 2025-02-25 13:39:40 | rand=94084

Auto-commit on 2025-02-25 13:51:43 | rand=4341

Auto-commit on 2025-02-25 14:03:44 | rand=24208

Auto-commit on 2025-02-25 14:15:51 | rand=65117

Auto-commit on 2025-02-25 14:27:54 | rand=81322

Auto-commit on 2025-02-25 14:40:02 | rand=44671

Auto-commit on 2025-02-25 14:52:05 | rand=49800

Auto-commit on 2025-02-25 15:04:13 | rand=99042

Auto-commit on 2025-03-06 14:43:45 | rand=50250

Auto-commit on 2025-03-06 14:57:16 | rand=49623

Auto-commit on 2025-03-06 15:08:36 | rand=99240

Auto-commit on 2025-03-06 15:20:02 | rand=10250

Auto-commit on 2025-03-06 15:56:18 | rand=78319

Auto-commit on 2025-03-06 16:07:38 | rand=75343

Auto-commit on 2025-03-06 16:18:55 | rand=47239

Auto-commit on 2025-03-06 16:30:11 | rand=89004

Auto-commit on 2025-03-06 16:41:31 | rand=10264

Auto-commit on 2025-03-06 16:52:49 | rand=47069

Auto-commit on 2025-03-06 17:04:06 | rand=48768

Auto-commit on 2025-03-06 20:04:21 | rand=67955

Auto-commit on 2025-03-06 20:44:17 | rand=67838

Auto-commit on 2025-03-06 20:56:09 | rand=57386
