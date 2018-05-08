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

```javascript
'use strict';
var startTime = new Date().getTime();
var count = 0;
var TD = 0;
var
demand = require('must'),
fs        = require('fs'),
path      = require('path'),
Blake2    = require('./index');
var startTime = new Date().getTime();
var count = 0;
var TD = 0;
var assert = require('assert');
var buf = new Buffer('abc');
var hash = Blake2.sumBuffer(buf, Blake2.ALGORITHMS.B);
assert(hash instanceof Buffer);
console.log('Blake2b:');
console.log(hash.toString('hex'));
var endTime = new Date().getTime();
TD = endTime  - startTime;
while ((endTime  - startTime) < 5000) {
    var hash = Blake2.sumBuffer(buf, Blake2.ALGORITHMS.B);
    assert(hash instanceof Buffer);
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
var assert = require('assert');
var buf = new Buffer('abc');
var hash2 = Blake2.sumBuffer(buf, Blake2.ALGORITHMS.S);
assert(hash2 instanceof Buffer);
console.log('Blake2s:');
console.log(hash2.toString('hex'));
var endTime = new Date().getTime();
TD = endTime  - startTime;
while ((endTime  - startTime) < 5000) {
    var hash2 = Blake2.sumBuffer(buf, Blake2.ALGORITHMS.S);
    assert(hash2 instanceof Buffer);
    var endTime = new Date().getTime();
    count++;}
console.log('Number of hashes generated during 5 seconds:');
console.log(count)
```

```javascript
'use strict';
var test = require('tape')
var ed = require('./')
var bindings = require('./build/Release/supercop.node')
var startTime = new Date().getTime();
var count = 0;
var TD = 0;
test('generate, sign, and verify', function (t) {
  var endTime = new Date().getTime();
  TD = endTime  - startTime;
  while ((endTime  - startTime) < 5000) {
  t.plan(7)
  var seed = ed.createSeed()
  t.equal(seed.length, 32)
  var kp = ed.createKeyPair(seed)
  t.equal(kp.publicKey.length, 32)
  t.equal(kp.secretKey.length, 64)
  var msg = 'whatever'
  var sig = ed.sign(msg, kp.publicKey, kp.secretKey)
  var xsig = xmod(sig)
  var xmsg = xmod(msg)
  var xpk = xmod(kp.publicKey)
  t.ok(ed.verify(sig, msg, kp.publicKey))
  t.notOk(ed.verify(xsig, msg, kp.publicKey))
  t.notOk(ed.verify(sig, xmsg, kp.publicKey))
  t.notOk(ed.verify(sig, msg, xpk))
  var endTime = new Date().getTime();
  count++;}
console.log('Number of hashes generated during 5 seconds:');
console.log(count)
})
function xmod (buf) {
  var cp = Buffer(buf)
  cp[0] = ~cp[0]
  return cp}
```
<html><math><mover><mi>k</mi><mo>~</mo></mover></math></html>
