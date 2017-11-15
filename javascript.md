# JavaScript

## Arrays

Suppose I have

```js
let array = [1,2,3]
let copy = array
```
If I do

```js
array = []
```
`array` is now [], but `copy` is still `[1,2,3]`. However, if I do

```js
array.length = 0
```
`array` is now `[]` and `copy` is also `[]`. Kinda cool. Still don't know why exactly...but neat.