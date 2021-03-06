# All Variations

A tagged template literal that compiles all variations of array contents.

## Usage

```js
import all from 'all-variations'

const foo = ['foo', 'bar', 'baz']
const num = [1, 2, 3]
const jandals = 'jandals'

const allVariations = all`${num}: ${foo}bar ${jandals}`
/*
[
  '1: foobar jandals',
  '1: barbar jandals',
  '1: bazbar jandals',
  '2: foobar jandals',
  etc...
]
*/
```

There is also a generator implementation that avoids loading all the variations into memory at once.

```js
import all from 'all-variations/generator'

const foo = ['foo', 'bar', 'baz']
const num = [1, 2, 3]
const jandals = 'jandals'

const allVariations = all`${num}: ${foo}bar ${jandals}`
for (let variation of allVariations) {
  console.log(variation)
}
/*
Logs:
'1: foobar jandals',
'1: barbar jandals',
'1: bazbar jandals',
'2: foobar jandals',
etc...
*/
```
