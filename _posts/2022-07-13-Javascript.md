---
layout: post
title: JavaScript
category: Programming Language
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/13/JavaScript/
---

REPL - Read Evaluate Print Loop

#### JavaScript Arrays

Arrays are the ordered collection of values.

```js:
let students = []; //empty array
let colors = ['red', 'orange', 'yellow']; // string array
let numbers = [19,22,56,12,51]; // number array
let stuff = [true, 68, 'cat', null]; // mixed array

numbers.length // will give you the length
[].length // 0
colors[1][0] // o
```
Modifying Arrays

```js:
let colors = ['rad', 'orange', 'yellow'];
colors[0] = 'red' // rad -> red
colors[10] = 'indigo' // ['red', 'orange', 'yellow', emptyx7, 'indigo']
```

Array methods
Push - add to the end
Pop - remove from end
Shift - remove from start
Unshift - add to start
concat - merge arrays
includes - look for a value
indexOf - just like string.indexOf
join - create a string from an array
reverse - reverse an array
slice - copies a portion on an array
splice - removes/replaces elements
sort - sort an array

```js:
let movieLine = ['tom', 'nancy'];
movieLine.push('pablo') // adds pablo at the end
movieLine.push('eva', 'oliver')

movieLine.pop() // removes oliver

movieLine.shift() // removes and returns tom
movieLine.unshift('harry') // adds at the first index


const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);


let beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];
console.log(beasts.indexOf('bison')); // returns 1


```