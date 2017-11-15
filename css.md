# CSS

**Table of Contents**
* [Custom Properties](#custom-properties)

## Custom Properties

Let's say I'm using a [Tachyons](https://github.com/tachyons-css/tachyons) style CSS system/framework/what-have-you, and I want a bunch of different padding left styles. I could have:

```css
.pad-l-1 {
  padding-left: 1px;
}

.pad-l-2 {
  padding-left: 2px;
}
...
```
And on and on until I have everything. Now this would be good if I have a couple base padding levels I use in my design. I could also use custom properites like so:

```css
.pad-l-x {
  padding-left: var(--pad-l);
}
```
Here, the custom property will not be defined by the css, but rather in the HTML.

```html
<div class="pad-l-x" style="--pad-l: 12px;"></div>
<div class="pad-l-x" style="--pad-l: 6px;"></div>
```
Both `div`s take advantage of the same class, but define the custom propery differently.

I'm not sure how useful this is yet, or if it's useful at all at this point. You could just do:

```html
<div style="padding-left: 12px;"></div>
<div style="padding-left: 6px;"></div>
```
I'm still playing around with this to see if I can find any more uses for it. It's probably most useful if you are setting properties on psuedo elements.

[Here's a little example](https://codepen.io/samwarnick/pen/EbvNNL)

---
**Sources**

[https://css-tricks.com/css-attr-function-got-nothin-custom-properties/](https://css-tricks.com/css-attr-function-got-nothin-custom-properties/)
