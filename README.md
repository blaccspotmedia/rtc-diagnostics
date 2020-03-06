# Twilio Diagnostics SDK
The Diagnostics SDK provides the tools for the developer to determine Voice & Video calling readiness. The SDK provides the methods necessary to identify where the issues are and to provide a mechanism of estimating expected audio quality.

* [API Docs](https://twilio.github.io/sdk-diagnostics/globals.html)
* Quickstart (Coming soon)
* Changelog (Coming soon)

Usage
------------
The following is an example for running bitrate test. For more information, please refer to the [API Docs](https://twilio.github.io/sdk-diagnostics/globals.html)

```ts
import { testBitrate } from '@twilio/diagnostics';

const bitrateTest = testBitrate({
 iceServers: [{
   credential: 'bar',
   username: 'foo',
   urls: 'turn:global.turn.twilio.com:3478?transport=udp',
 }],
});

bitrateTest.on('bitrate', (bitrate) => {
 console.log(bitrate);
});

bitrateTest.on('error', (error) => {
 console.log(error);
});

bitrateTest.on('end', (report) => {
 console.log(report);
});

setTimeout(() => {
 bitrateTest.stop();
}, 10000);
```

Installation
------------

```
git clone git@github.com:twilio/sdk-diagnostics.git
cd sdk-diagnostics
npm install
```

Commands
------------

* `npm run build` - builds the artifacts under `dist` folder
* `npm run test` - runs unit and integration tests
