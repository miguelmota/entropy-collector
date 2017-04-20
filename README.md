# EntropyCollector

> Collects random bits from mouse moves and keystrokes and estimates the amount of Shannon entropy among collected samples.

*Note: This is a fork of [vibornoff/entropy-collector.js](https://github.com/vibornoff/entropy-collector.js).*

## Install

```bash
npm install entropy-collector
```

## Quick start

Add `<script src="path/to/entropy-collector.js"></script>` into your page,<br />
or use require if using NPM `var EntropyCollector = require('entropy-collector');`.

Instantiate class, `var entropyCollector = new EntropyCollector();`.

Place `entropyCollector.start()` into a suitable place.

Move your mouse and press keys for a couple of seconds and right after
get the entropy estimation from `entropyCollector.estimatedEntropy`
and the noisy bits from `entropyCollector.buffer`.

Don't forget to call `entropyCollector.stop()` whenever you decide to stop
entropy collection.

## Reference

### entropyCollector.eventTarget

DOM *EventTarget* to consume events from. Uses `document` as default target.
Setting new target will stop previously started collectors on the old target.

### entropyCollector.start

Starts entropy collection at the current target.

### entropyCollector.stop

Stops entropy collection at the current target.

### entropyCollector.eventsCaptured

The number of events captured.

### entropyCollector.estimatedEntropy

Estimated amount of Shannon entropy of collected samples.

### entropyCollector.buffer

*ArrayBuffer* containing the noisy bits.
Use it to seed [CPRNG](http://en.wikipedia.org/wiki/Cryptographically_secure_pseudorandom_number_generator)
or to derive a cryptographic key with a [secure hash function](http://en.wikipedia.org/wiki/Cryptographic_hash_function).

**DON'T USE THESE BITS DIRECTLY**

TODO
----

Add support of mobile devices (acceletometer and g-sensor entropy collection).

## License

MIT
