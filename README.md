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

Auto-commit on 2025-02-18 17:15:46 | rand=58962

Auto-commit on 2025-02-18 17:28:14 | rand=64395

Auto-commit on 2025-02-18 17:29:41 | rand=19909

Auto-commit on 2025-02-18 18:24:14 | rand=64814

Auto-commit on 2025-02-18 18:37:04 | rand=61141

Auto-commit on 2025-02-18 18:49:57 | rand=84788

Auto-commit on 2025-02-18 19:02:50 | rand=63973

Auto-commit on 2025-02-18 19:15:40 | rand=79617

Auto-commit on 2025-02-18 19:28:28 | rand=65575

Auto-commit on 2025-02-18 19:41:24 | rand=93914

Auto-commit on 2025-02-18 19:54:17 | rand=63603

Auto-commit on 2025-02-18 20:07:10 | rand=18660

Auto-commit on 2025-02-18 20:20:03 | rand=67913

Auto-commit on 2025-02-18 20:32:56 | rand=28092

Auto-commit on 2025-02-18 20:45:51 | rand=75361

Auto-commit on 2025-02-18 20:58:44 | rand=34436

Auto-commit on 2025-02-18 21:11:38 | rand=73267

Auto-commit on 2025-02-18 21:24:30 | rand=28205

Auto-commit on 2025-02-19 08:14:17 | rand=61742

Auto-commit on 2025-02-19 08:27:10 | rand=86770

Auto-commit on 2025-02-19 08:40:11 | rand=61997

Auto-commit on 2025-02-19 08:53:08 | rand=98903

Auto-commit on 2025-02-19 09:05:58 | rand=86974

Auto-commit on 2025-02-19 09:18:56 | rand=24676

Auto-commit on 2025-02-19 09:31:55 | rand=73767

Auto-commit on 2025-02-19 09:44:51 | rand=6326

Auto-commit on 2025-02-19 09:57:45 | rand=87909

Auto-commit on 2025-02-19 10:10:44 | rand=50818

Auto-commit on 2025-02-19 10:23:33 | rand=65115

Auto-commit on 2025-02-19 10:36:26 | rand=10777

Auto-commit on 2025-02-19 10:49:23 | rand=88486

Auto-commit on 2025-02-19 11:02:16 | rand=20917

Auto-commit on 2025-02-19 11:15:12 | rand=85540

Auto-commit on 2025-02-19 18:26:34 | rand=98438

Auto-commit on 2025-02-19 18:39:33 | rand=53932

Auto-commit on 2025-02-19 18:52:30 | rand=73835

Auto-commit on 2025-02-19 19:05:19 | rand=32178

Auto-commit on 2025-02-19 19:18:18 | rand=40335

Auto-commit on 2025-02-19 19:31:10 | rand=90501

Auto-commit on 2025-02-19 19:44:03 | rand=19379

Auto-commit on 2025-02-19 19:57:01 | rand=72993

Auto-commit on 2025-02-19 20:09:55 | rand=77757

Auto-commit on 2025-02-19 20:22:51 | rand=94232

Auto-commit on 2025-02-19 20:35:48 | rand=24118

Auto-commit on 2025-02-19 20:48:41 | rand=83078

Auto-commit on 2025-02-19 21:01:43 | rand=36062

Auto-commit on 2025-02-19 21:14:36 | rand=24805

Auto-commit on 2025-02-19 21:27:35 | rand=30279

Auto-commit on 2025-02-20 09:32:48 | rand=20575

Auto-commit on 2025-02-20 09:45:51 | rand=52550

Auto-commit on 2025-02-20 14:09:31 | rand=7536

Auto-commit on 2025-02-20 14:21:37 | rand=43939

Auto-commit on 2025-02-20 14:33:44 | rand=36212

Auto-commit on 2025-02-20 14:45:47 | rand=67310

Auto-commit on 2025-02-20 14:57:44 | rand=40408

Auto-commit on 2025-02-20 15:09:51 | rand=36611

Auto-commit on 2025-02-20 15:21:51 | rand=92611

Auto-commit on 2025-02-20 15:33:57 | rand=95111

Auto-commit on 2025-02-20 15:46:04 | rand=50182

Auto-commit on 2025-02-20 15:58:09 | rand=58947

Auto-commit on 2025-02-20 16:10:15 | rand=98424

Auto-commit on 2025-02-20 16:22:22 | rand=22368

Auto-commit on 2025-02-20 16:34:29 | rand=96659

Auto-commit on 2025-02-20 16:46:33 | rand=29671

Auto-commit on 2025-02-20 16:58:40 | rand=98293

Auto-commit on 2025-02-21 15:12:20 | rand=37291

Auto-commit on 2025-02-21 15:24:27 | rand=23369

Auto-commit on 2025-02-21 15:36:26 | rand=7666

Auto-commit on 2025-02-21 15:48:25 | rand=75514

Auto-commit on 2025-02-21 16:00:21 | rand=43373

Auto-commit on 2025-02-21 16:12:18 | rand=26135

Auto-commit on 2025-02-21 16:24:17 | rand=41979

Auto-commit on 2025-02-21 16:36:21 | rand=12796

Auto-commit on 2025-02-21 16:48:25 | rand=21217

Auto-commit on 2025-02-21 17:00:21 | rand=83542

Auto-commit on 2025-02-21 17:12:22 | rand=7773

Auto-commit on 2025-02-21 17:24:20 | rand=21597

Auto-commit on 2025-02-21 17:36:19 | rand=35348

Auto-commit on 2025-02-21 17:48:17 | rand=16812

Auto-commit on 2025-02-21 18:00:18 | rand=3730

Auto-commit on 2025-02-22 00:18:33 | rand=31444

Auto-commit on 2025-02-22 00:30:39 | rand=21370

Auto-commit on 2025-02-22 00:42:44 | rand=38330

Auto-commit on 2025-02-22 00:54:46 | rand=6054

Auto-commit on 2025-02-22 01:06:49 | rand=52801

Auto-commit on 2025-02-22 01:18:56 | rand=17568

Auto-commit on 2025-02-22 01:30:56 | rand=99807

Auto-commit on 2025-02-22 01:42:59 | rand=20842

Auto-commit on 2025-02-22 01:55:01 | rand=17658

Auto-commit on 2025-02-22 02:07:09 | rand=58257

Auto-commit on 2025-02-22 02:19:15 | rand=60704

Auto-commit on 2025-02-22 02:31:23 | rand=46010

Auto-commit on 2025-02-22 02:43:28 | rand=93159

Auto-commit on 2025-02-22 02:55:27 | rand=48774

Auto-commit on 2025-02-22 03:07:45 | rand=29495

Auto-commit on 2025-02-22 14:47:40 | rand=25563

Auto-commit on 2025-02-22 14:59:50 | rand=95127

Auto-commit on 2025-02-22 15:11:55 | rand=67167

Auto-commit on 2025-02-22 15:24:00 | rand=60459

Auto-commit on 2025-02-22 15:36:00 | rand=32829

Auto-commit on 2025-02-22 15:48:07 | rand=6694

Auto-commit on 2025-02-22 16:00:13 | rand=29400

Auto-commit on 2025-02-22 16:12:11 | rand=50163

Auto-commit on 2025-02-22 16:24:13 | rand=82929

Auto-commit on 2025-02-22 16:36:13 | rand=24610

Auto-commit on 2025-02-22 16:48:17 | rand=96923

Auto-commit on 2025-02-22 17:00:17 | rand=32691

Auto-commit on 2025-02-22 17:12:24 | rand=85096

Auto-commit on 2025-02-22 17:24:28 | rand=447

Auto-commit on 2025-02-22 17:36:34 | rand=46064

Auto-commit on 2025-02-24 13:51:21 | rand=67790

Auto-commit on 2025-02-24 14:03:21 | rand=86964

Auto-commit on 2025-02-24 14:15:20 | rand=16290

Auto-commit on 2025-02-24 14:27:29 | rand=39354

Auto-commit on 2025-02-24 14:39:35 | rand=6926

Auto-commit on 2025-02-24 14:51:36 | rand=7404

Auto-commit on 2025-02-24 15:03:43 | rand=53599

Auto-commit on 2025-02-24 15:15:46 | rand=44375

Auto-commit on 2025-02-24 15:27:54 | rand=62421

Auto-commit on 2025-02-24 15:40:05 | rand=89725

Auto-commit on 2025-02-24 15:52:14 | rand=9267

Auto-commit on 2025-02-24 16:04:16 | rand=17745

Auto-commit on 2025-02-24 16:16:13 | rand=67280

Auto-commit on 2025-02-24 16:28:19 | rand=77971

Auto-commit on 2025-02-24 16:40:22 | rand=85521

Auto-commit on 2025-02-24 17:52:36 | rand=28718

Auto-commit on 2025-02-24 18:04:36 | rand=87691

Auto-commit on 2025-02-24 18:16:41 | rand=38072

Auto-commit on 2025-02-24 18:28:45 | rand=83291

Auto-commit on 2025-02-24 18:40:56 | rand=68147

Auto-commit on 2025-02-24 18:52:57 | rand=57919

Auto-commit on 2025-02-24 19:05:10 | rand=10213
