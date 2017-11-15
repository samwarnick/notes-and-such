# JavaScript

**Table of Contents**
* [Arrays](#arrays)
  * [Length](#length)

## Arrays

### Length
Suppose I have

```js
let array = [1, 2, 3]
let copy = array
```
If I do

```js
array = []
```
`array` is now [], but `copy` is still `[1, 2, 3]`. However, if I do

```js
array.length = 0
```
`array` is now `[]` and `copy` is also `[]`. Kinda cool.

This is becasue `array.length = 0` is modifying the actual array. In the first case, `array = []` is creating a new array, changing the reference. So `array` now has a new reference, but `copy` is still pointing to the old reference.

Now, `array.length = 0` is not the most clear. So you can do something like

```js
Array.prototype.clear = function () {
  this.length = 0
}
```
and use like

```js
let array = [1, 2, 3]
array.clear() // array is now []
```

I made [this dumb little "library"](https://github.com/samwarnick/array-clear) to do that.

**Side Note**
```js
let array = [1,2,3]
array.length = 2 // array is now [1, 2]
array.length = 4 // array is now [1, 2, undefined, undefined]
```
