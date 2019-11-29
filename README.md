
# Hades-js

Don't use this module comercially. It's not stable and I'm still working on the tests and improvements like retrogrades, mid-points, etc.

### Features

- Planetary positions from a geocentric point of view.
- Placidus and Fixed house systems.
- ASC, MC, Julian day and sidereal time.

#### Install

`$ npm install @goldenius/hades-js`

#### Usage

At the moment you may only get data for dates between 1900-2050. This is because Hades at the moment does not calculate the points from scratch. It relies on ephemeris (check the resources folder) fed into it.

Before using this module, it's necessary to load the resources:
```javascript
const {Astrologer} = require("@goldenius/hades-js")
let astrologer = new Astrologer();
await astrologer.Init();
```

The easiest way to retrieve planetary positions with aspects and house calculations is to input:
- date and time (momentjs date object)
- timezone
- geodetic location

for example:
```javascript

const {Astrologer} = require('../distribution/index.js');
const moment = require('moment-timezone');

let astrologer = new Astrologer();
await astrologer.Init();
let planets = astrologer.CalculateCelestialBodiesAndTime(moment(),"GB",{latitude:33,longitude:55});
console.log(JSON.stringify(planets));


```
