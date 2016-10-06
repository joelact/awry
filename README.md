# awry

[![Build Status][Build Status Image]][Build Link]
[![Code Climate][Code Climate GPA Image]][Code Climate Link]
[![Test Coverage][Test Coverage Image]][Test Coverage Link]

An [Asterisk REST Interface][] websocket and API client library for node.js
v6+.

#### installation

`npm install awry`

#### example

```js
const awry = require('awry');

const api = new awry.API({
  baseUrl: 'http://asterisk.local:8088/ari',
  username: 'asterisk',
  password: 'asterisk'
});

api.applications.list().then(apps => {
  console.log(apps);
});

const events = awry.Events.connect({
  app: 'someApp',
  url: 'http://asterisk.local:8088/ari/events',
  username: 'asterisk',
  password: 'asterisk'
});

events.on('message', message => {
  console.log(message);
});
```

### license
[MIT](LICENSE-MIT)

[Asterisk REST Interface]: https://wiki.asterisk.org/wiki/pages/viewpage.action?pageId=29395573
[Build Status Image]: https://travis-ci.org/chadxz/awry.svg?branch=master
[Build Link]: https://travis-ci.org/chadxz/awry
[Test Coverage Image]: https://codeclimate.com/github/chadxz/awry/badges/coverage.svg
[Test Coverage Link]: https://codeclimate.com/github/chadxz/awry/coverage
[Code Climate GPA Image]: https://codeclimate.com/github/chadxz/awry/badges/gpa.svg
[Code Climate Link]: https://codeclimate.com/github/chadxz/awry
[Dependencies Status Image]: https://david-dm.org/chadxz/awry.svg
[Dependencies Status Link]: https://david-dm.org/chadxz/awry
