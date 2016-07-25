# JavaScript Arrays and Loops

## Learning Objectives

* Explain the advantages of using Arrays
* Declare an Array in JavaScript
* Access elements in an Array
* Use the `for` loop to iterate through the elements in an Array
* Use `push` and `pop` to add and remove elements from an Array
* Use `shift` and `unshift` to add and remove elements from an Array
* Use `splice` and `slice` to access and manipulate sections of an Array
* Compare the classic `for` loop with the newer `forEach` loop

## Introduction

Q: What is an array?

A: A data structure for storing a collection of values in a single variable.

Q: What is a data structure?

A: A construct for structuring data (duh)

## Encapsulation

We often have a *lot* of moving parts in a program. We want to organize these parts into logical building blocks.

An array is a simple way of _encapsulating_ a collection of values into a single _object_.

## JavaScript Arrays

### Declaring

```javascript
// declare an array of colors
var colors = [];              // an empty array        <-- preferred
var colors = new Array();     // also an empty array   <-- can be dangerous!
var colors = ['red', 'green', 'blue'];    // an array of colors
```

### Accessing

> Note: in most modern programming languages, including JavaScript, arrays are indexed starting with zero!

```javascript
var colors = ['red', 'green', 'blue'];    // an array of colors
var first = colors[0];                    // 'red'
var second = colors[1];                   // 'green'
var third = colors[2];                    // 'blue'
```

### Modifying

* push() adds at end;
* pop() deletes from end.
* unshift() adds to front;
* shift() deletes from front.
* splice() can do whatever it wants, wherever it wants.

```javascript
colors.push('yellow');                    // add to the end of the array
colors.pop();                             // remove an item from the end of the array
colors.unshift('purple');
colors.shift();
colors.splice();
```

`splice(index, howmany, item1, ....., itemX)`:

* index: Required. An integer that specifies at what position to add/remove items, Use negative values to specify the position from the end of the array.
* howmany: Required. The number of items to be removed. If set to 0, no items will be removed.
* item1, ..., itemX: Optional. The new item(s) to be added to the array at `index`

`splice` returns an array of the items that were removed.

### Summary of Array Functions

```javascript
var array = [1, 2, 3];

array.push();         // Adds one or more elements to the end of an array and returns the new length of the array.
array.pop();          // Removes the last element from an array and returns that element.
array.unshift();      // Adds one or more elements to the front of an array and returns the new length of the array.
array.shift();        // Removes the first element from an array and returns that element.
array.splice();       // Adds and/or removes elements from an array.
array.slice();        // Extracts a section of an array and returns a new array.
array.concat();       // Returns a new array comprised of this array joined with another array
array.reverse();      // Reverses the order of the elements of an array
array.sort();         // Sorts the elements of an array in place and returns the array.
array.join();         // Joins all elements of an array into a string.
array.toString();     // Converts an array into a string.
array.reduce();       // Reduce the array to a single value using the provided callback.
array.map();          // Map each value in the array to a new value using the provided callback.
```

### Iteration

There are 2 ways to iterate over an array:

#### The Classic `for` Loop

```javascript
fruit = ['Apple', 'Orange', 'Banana'];

for (var i=0, len=fruit.length; i < len; i++) {
  console.log(fruit[i]);
}
```

Let's examine the syntax for the classic `for` loop:

* There are always 2 semicolons in the for loop iteration expression. So we have:

```javascript
for (initialExpression ; iterationTest ; iterationIncrement) {
  // block of code to execute for each iteration
}
```

* The `initialExpression` runs once at the beginning of the iterations
* The `iterationTest` runs before each iteration, if it is falsey then the for loop ends
* The `iterationIncrement` runs after each iteration

Another example:

```javascript
for (var i=1; i<=10; i++) {
  console.log('i = ' + i);
}
```

#### The Newer `forEach` Loop

```javascript
fruit = ['Apple', 'Orange', 'Banana'];

fruit.forEach(function(item) {
  console.log(item);
});
```

What are the advantages and disadvantages of each?

* [How to iterate over an array](http://stackoverflow.com/questions/9329446/for-each-over-an-array-in-javascript)

### Code Along - Multiplication Table

Write a JavaScript function that will print out the multiplication table from "1 x 1 = 1" to "12 x 12 = 12".

You can view the solution [here](solutions/mult-table.js).

> Note: This example shows that you don't always need an array to use a `for` loop.

### LAB 1 - Sum the elements of an Array

Write a program to sum the elements of an Array (assume all of the elements are numbers):

Starter:

```javascript
var numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];

var sum = 0;

// TODO: add a for loop here to add up all of the numbers into the variable sum

console.log('sum = ' + sum);
```

Solutions are below:

* [Classic For Loop Solution](solutions/array-sum-1.js)
* [Solution using reduce](solutions/array-sum-2.js)

> Wow, the second solution is only 3 lines of code and we don't need a loop at all!!!

### LAB 2 - Add the elements of 2 Arrays Together

Write a program to add all of the elements of 2 arrays together. For instance, given the arrays:

```javascript
var x = [1, 2, 3];
var y = [4, 5, 6];
```

The sum of the arrays is [5, 7, 9].

Starter:

```javascript
// add 2 integer arrays (add elements)
function sumOfArrays(a, b) {
  var result = [];
  // TODO: write a for loop that adds the elements of a and b.
  //       and pushes each sum into the result array.
  return result;
}

var a = [1, 2, 3];
var b = [4, 6, 8];
console.log("sum of arrays = " + sumOfArrays(a, b));
```

You can view the solution [here](solutions/add-2-arrays.js).

Bonus (work in pairs): Assume that the arrays may be of different lengths and assume zero values for the shorter array:

You can view the solution [here](solutions/add-2-arrays-bonus.js).

You can view an even shorter bonus solution [here](add-2-arrays-bonus-2.js).

### Multi-Dimensional Arrays

```javascript
var board = [ [ 'X', 'O', 'X' ],
              [ 'O', 'X', 'O' ],
              [ 'X', 'O', 'X' ]
            ];
```

### LAB 3 - Print Tic Tac Toe Board - PAIR UP!!!

Write a program to print the above board in a nice format.
Hint: only use a single for loop (not nested for loops).

You can view the solution [here](solutions/print-tic-tac-toe.js).
