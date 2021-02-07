---
layout: default
title: How to Swap Values in One Line with javascript
date: 2021-02-08 00:55:00 -0900
tags: javascript
---

# {{ page.title }}
{{ page.date }}
## Introduction
I want swap values with javascript.

We often face to the situation where swapping values. For example, swapping contents in arrays. However, javascript does not prepare swap function basically. In this post, I introduce some solutions to swap values and suppose the situation we should swap values in the same array for simplicity. So, we want to do as follows.

```js
let array = [1, 2, 3, 4, 5];

// Swap array[0] and array[4]
// Coding here!

console.log(array);
// Output -> [5, 2, 3, 4, 1]
```

## Solutions
### Solution 1 - Simple Honesty
Prepare escaping member such as `temp`.
```js
let temp = array[0];
array[0] = array[4];
array[4] = temp;
```
It is one of the basic solutions, but when we want to swap more than three values, this solution needs multiple lines for swapping processing like this...
```js
let temp = array[0];
array[0] = array[2];
array[2] = array[4];
array[4] = temp;
```

### Solution 2 - One Liner
On the other hand, the following solution is very simple.
```js
[array[0], array[4]] = [array[4], array[0]];
```
In addition, this solution covers swapping more than three values like this...
```js
[array[0], array[2], array[4]] = [array[2], array[4], array[0]];
```
We can code multiple-values-swapping with only one line.

## Conclusion
By applying *array matching*, we can swap multiple values in one line.

## Reference
- [ECMAScript 6: New Features: Overview and Comparison](http://es6-features.org/#ArrayMatching)