# ކޮފީ_ޕްލަސް އެވެ

[@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , ކޮފީސްކްރިޕްޓް ސިންޓެކްސްގެ މައްޗަށް ބިނާކޮށް ބައެއް ފީޗާސްތައް އިތުރުކުރުން، [coffee_plus](./coffee_plus.md) ބައްލަވާށެވެ.

## ޑިކްލެއަރ ވެރިއޭބަލް

```
+ var1, var2
```

## ޑިކްލެރޭޝަން ލޭބަލް

`:$` އަކީ [ސްވެލްޓް](https://svelte.dev/docs#component-format-script-3-$-marks-a-statement-as-reactive) އާއި އެކު ބޭނުން ކުރުމަށްޓަކައެވެ .

```
do =>
  :out
    for i in [1,2,3]
      for j in [4,5,6]
        console.log i,j
        if i > 1
          break out
  return

y = 0

:$ x=y*2

:$ if y>2 then x+=y else x-=y

:$
  if x > y
    x = y/2
  else
    x = y+9
  x += 1

:$ func = => 1

:$ func = ->
  1
  2
```

އަށް ކޮމްޕައިލް ކުރާނެއެވެ

```
var func, x, y;

(() => {
  var i, j, k, l, len, len1, ref, ref1;
  out : {
    ref = [1, 2, 3];
    for (k = 0, len = ref.length; k < len; k++) {
      i = ref[k];
      ref1 = [4, 5, 6];
      for (l = 0, len1 = ref1.length; l < len1; l++) {
        j = ref1[l];
        console.log(i, j);
        if (i > 1) {
          break out;
        }
      }
    }
  }
})();

y = 0;

$ : x = y * 2;

$ : y > 2 ? x += y : x -= y;

$ : {
  if (x > y) {
    x = y / 2;
  } else {
    x = y + 9;
  }
  x += 1;
}

$ : (func = () => {
  return 1;
});

$ : (func = function() {
  1;
  return 2;
});
```

## އަވަސް އިމްޕޯޓް

```
> zx/globals:
  @w5/walk:@ > walkRel
  @w5/u8 > U8 u8eq u8merge
  @w5/snake > SNAKE
  @w5/write
  @w5/xxhash3-wasm
```

އަށް ކޮމްޕައިލް ކުރާނެއެވެ

```
import 'zx/globals';

import walk from '@w5/walk';

import {
  walkRel
} from '@w5/walk';

import {
  U8,
  u8eq,
  u8merge
} from '@w5/u8';

import {
  SNAKE
} from '@w5/snake';

import write from '@w5/write';

import Xxhash3Wasm from '@w5/xxhash3-wasm';
```
