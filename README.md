A polyphonic microtonal mixer synthesizing audio carriers across a 72-EDO tuning matrix.

2026/10/26 - 13:37
Observation: this is a primitive version of the acoustic alternative to the BPE tokenizer.

the core of this program is:

```js
const freq = 261.63 * Math.pow(2, (charCode % 72) / 72.0);
const masterSpeed = parseFloat(speedSlider.value) || 1.0;
const duration = ((45 + ((charCode * 5) % 6) * 20) / 1000.0) / masterSpeed;

ch.oscNode.frequency.setValueAtTime(freq, time);
...
ch.nextNoteTime += duration
```
