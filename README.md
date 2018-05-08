# Test
create this just for test
```javascript
'use strict';
var startTime = new Date().getTime();
var count = 0;
var TD = 0;
var test = require('tape')
var Blake2b = require('./Blake2b')
var util = require('./util')
var fs = require('fs')
var Blake2bHex = Blake2b.Blake2bHex
var hash = Blake2bHex('abc');
console.log('Blake2b result for input array "abc"');
console.log(hash.toString('hex'));
var endTime = new Date().getTime();
TD = endTime  - startTime;
while ((endTime  - startTime) < 5000){
    var hash = Blake2bHex('abc');
    var endTime = new Date().getTime();
    count++;}
console.log('Number of hashes generated during 5 seconds:');
console.log(count)
```

```javascript
'use strict';
var startTime = new Date().getTime();
var count = 0;
var TD = 0;
var test = require('tape')
var toHex = require('./util').toHex
var util = require('./util')
var b2s = require('./Blake2s')
var Blake2s = b2s.Blake2s
var Blake2sHex = b2s.Blake2sHex
var Blake2sInit = b2s.Blake2sInit
var Blake2sUpdate = b2s.Blake2sUpdate
var Blake2sFinal = b2s.Blake2sFinal
var hash = Blake2sHex('abc');
console.log('Blake2s result for input array "abc"');
console.log(hash.toString('hex'));
var endTime = new Date().getTime();
TD = endTime  - startTime;
while ((endTime  - startTime) < 5000) {
    var hash = Blake2sHex('abc');
    var endTime = new Date().getTime();
    count++;}
console.log('Number of hashes generated during 5 seconds:');
console.log(count)
```
