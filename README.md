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

Auto-commit on 2025-02-05 21:37:00 | rand=20873

Auto-commit on 2025-02-05 23:30:40 | rand=99066

Auto-commit on 2025-02-06 08:48:31 | rand=16691

Auto-commit on 2025-02-06 09:27:51 | rand=46396

Auto-commit on 2025-02-06 14:42:21 | rand=55758

Auto-commit on 2025-02-06 18:42:40 | rand=54749

Auto-commit on 2025-02-06 20:18:29 | rand=44015

Auto-commit on 2025-02-06 21:18:57 | rand=13347

Auto-commit on 2025-02-06 22:34:19 | rand=67847

Auto-commit on 2025-02-07 07:22:00 | rand=79278

Auto-commit on 2025-02-07 12:16:11 | rand=22245

Auto-commit on 2025-02-07 12:31:27 | rand=691

Auto-commit on 2025-02-07 16:32:15 | rand=17334

Auto-commit on 2025-02-07 18:23:29 | rand=34656

Auto-commit on 2025-02-07 21:38:57 | rand=24037

Auto-commit on 2025-02-07 22:47:48 | rand=9621

Auto-commit on 2025-02-08 07:28:41 | rand=64331

Auto-commit on 2025-02-08 11:15:59 | rand=55565

Auto-commit on 2025-02-08 11:58:09 | rand=54484

Auto-commit on 2025-02-08 23:10:17 | rand=62486

Auto-commit on 2025-02-09 17:56:18 | rand=42374

Auto-commit on 2025-02-09 18:06:00 | rand=67994

Auto-commit on 2025-02-10 09:34:04 | rand=53019

Auto-commit on 2025-02-10 13:52:33 | rand=97339

Auto-commit on 2025-02-10 17:22:44 | rand=45187

Auto-commit on 2025-02-12 10:09:09 | rand=52438

Auto-commit on 2025-02-13 13:19:37 | rand=5501

Auto-commit on 2025-02-15 10:00:57 | rand=80774
