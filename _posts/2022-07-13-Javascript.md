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


let array1 = ['a', 'b', 'c'];
let array2 = ['d', 'e', 'f'];
let array3 = array1.concat(array2);




let beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];
console.log(beasts.indexOf('bison')); // returns 1

let elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// expected output: "Fire,Air,Water"

console.log(elements.join(''));
// expected output: "FireAirWater"

console.log(elements.join('-'));
// expected output: "Fire-Air-Water"



let array1 = ['one', 'two', 'three'];
console.log('array1:', array1);
// expected output: "array1:" Array ["one", "two", "three"]

let reversed = array1.reverse();
console.log('reversed:', reversed);
// expected output: "reversed:" Array ["three", "two", "one"]

// Careful: reverse is destructive -- it changes the original array.
console.log('array1:', array1);
// expected output: "array1:" Array ["three", "two", "one"]

let animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]

let months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// inserts at index 1
console.log(months);
// expected output: Array ["Jan", "Feb", "March", "April", "June"]

let months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);
// expected output: Array ["Dec", "Feb", "Jan", "March"]

let array1 = [1, 30, 4, 21, 100000];
array1.sort();
console.log(array1);
// expected output: Array [1, 100000, 21, 30, 4]

```

#### Reference Types and Equality Testing

```js:
 ['hi', 'bye'] === ['hi', 'bye'] // will return False
```
Javascript doesn't compare contents of the array, it compares the references in the memory.

```js:
let nums = [1, 2, 3];
let numsCopy = nums;
nums === numsCopy // will return True as it is comparing the reference.
```
*We can use const with an array, because while creating an array using const the variable name for example*
> const nums =[1,2,3,4]
*the reference of the nums is not changing, so we can change the values or contents of it.*
*But as soon as we try to assign the variable into something totally different or to new reference it will show an error.*

