# Week 12: Introduction to JavaScript (Part 2)

Now that you have an introduction to the basics of values (variables), data types, and operations in JavaScript, we have the building blocks in place to start developing behavior (or interactive programs) for our sites. However, to develop behavior, we need to understand how to structure the logic, which we can do with conditional statements, functions, and loops.

We'll also discuss start diving a bit deeper in to the browser environment, and begin to learn how JavaScript plays a role in interacting with the page at hand.

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript Files](#javascript-files)
- [Part 2: Controlling Flow](#part-2-controlling-flow)
  - [Conditional Statements](#conditional-statements)
    - [`if...else` statement](#ifelse-statement)
  - [Loops and iteration](#loops-and-iteration)
    - [`for` statement](#for-statement)
    - [`for...in` statement](#forin-statement)
  - [Functions](#functions)
    - [Defining Functions](#defining-functions)
    - [Calling functions](#calling-functions)
    - [Function scope](#function-scope)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## JavaScript Files

In Part 1, we discussed the introductory concepts of programming using the browser console and additional tools to gain a basic understanding. In reality, you'll most likely be interacting with JavaScript through the use of JavaScript Files that are linked through your HTML files.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
  </head>
  <body>
    ...
    <script src="script.js"></script>
  </body>
</html>
```

JavaScript files can be linked in both the `<head>` and `<body>` elements, however, it's best practice to include the file at the bottom of the `<body>` element so it will run after all of the content and styling has been loaded by the browser.

JavaScript files can also be organized in their own folders, just like CSS/Sass.

```
|-- scss/
|-- scripts/
|   | -- app.js
|   
|-- index.html
```

In the above example, your script tag would need to reference the script in its **relative location** to the index.html, ie. `<script src="scripts/app.js"></script>`.

This week, we'll work on controlling the flow of our code inside a JavaScript file. See the [exercise files here](exercise). Download the exercise files, open up the the `index.html` file in your browser, and open the `script.js` file in your editor.

## Part 2: Controlling Flow
  - Conditional Statements
  - Loops and iteration
  - Functions

JavaScript supports a compact set of statements, specifically control flow statements, that you can use to incorporate a great deal of interactivity in your programs.

### Conditional Statements

A conditional statement is a set of commands that executes if a specified condition is true. JavaScript supports two conditional statements: `if...else` and `switch`. You can perform the same conditional logic using both `if...else` and `switch` statements, however for the sake of time we'll only be covering `if...else` statements in this course. a 

#### `if...else` statement

Use the `if` statement to execute code if a logical condition is `true`. Use the optional else clause to execute a statement if the condition is `false`. An `if` statement looks as follows:

**Example:**
```js
if (condition) {
  statement_1;
} else {
  statement_2;
}
```
A condition can be any expression that evaluates to `true` or `false`.

If `condition` evaluates to `true`, `statement_1` is executed; otherwise, `statement_2` is executed. `statement_1` and `statement_2` can be any statement, including further nested `if` statements.

**Actual Example:**
```js
var today = '11/11';
var birthday = '01/01';

if (today === birthday) {
  console.log('Happy Birthday!');
} else {
  console.log('It is not your birthday, but have a nice day!');
}
```

You may also compound the statements using else if to have multiple conditions tested in sequence, as follows:

**Example:**
```js
if (condition_1) {
  statement_1;
} else if (condition_2) {
  statement_2;
} else if (condition_n) {
  statement_n;
} else {
  statement_last;
} 
```
**So what evaluates as `false`?**

Outside of a value simply being not true (ie. `var = 5; 5 > 7`), the following values will also evaluate to false:

```js
false
undefined
null
0
NaN // Not a Number
""  // Empty string
```

### Loops and iteration

Loops offer a quick and easy way to do "something" repeatedly. In JavaScript, there are several loop mechanism's, but the two most common which we'll focus on in this class are: `for`, and `for...in`. They both essentially do the same thing: repeat an action some number of times, however each one is used in different cases.

#### `for` statement

A `for` loop repeats until a specified condition evaluates to `false`. The most common reason to use `for` loops is to **iterate over an Array**.

**Example:**

```js
for ([initialExpression]; [condition]; [incrementExpression]){
  statement; // Executed on each iteration of loop
}
```

Let's break this down (in order of execution):

1. `[initialExpression]`: This expression usually initializes one or more loop counters. This expression can also declare variables, ie. `var i = 0`
2. `[condition]`: Similar to the `if...else` condition, the condition is evaluated, but on every loop. If the value of condition is `true`, the loop statements execute. If the value of condition is false, the for loop stops.
3. `statement`: If the condition is `true`, the statement will be executed.
4. `[incrementExpression]`: Executes (typically updating the increment variable), and returns to step 2.

Let's see a real-world example; let's say we are building a game and want to output to the console how many steps the user has taken in a certain direction.

**Actual Example:**

```js
for (var step = 0; step < 100; step++) {
  // Runs 100 times, with values of step 0 through 99.
  console.log('Walking east: Step - ' + step);
}
```

#### `for...in` statement

The `for...in` statement iterates a specified variable over an object. A `for...in` statement looks as follows:

**Example:**

```js
for (variable in object) {
  statements
}
```

The flow is similar to a regular `for` statement, but the loop is limited to the amount of properties available in an object.

**Actual Example:**

```js
var car = {
  make: 'Ford',
  model: 'Explorer'
}

for (var i in car) {
  var property = i;
  var value = car[i];
  console.log(i + ': ' + car[i]);
}
```


### Functions

Functions are a way of packaging functionality that you want to reuse, so whenever you want the functionality you can call a function by name (like a variable) rather than constantly rewriting the entire code. You have already seen some uses of functions above, for example:

```js
console.log('yo!');
```

Functions are one of the fundamental building blocks in JavaScript. To use a function, you must define it and then call it.

There are a few functions like `console.log`, ie. `document.querySelector` and `alert`, that are built into the browser for you to use whenever you like.

```js
alert('yo!');
```

If you see something that looks like a variable name, but has brackets — () — after it, it is probably a function. Functions often take arguments — bits of data they need to do their job. These go inside the brackets, separated by commas if there is more than one item.

#### Defining Functions

A function definition (also called a function declaration, or function statement) consists of the function keyword, followed by:
- The name of the function.
- A list of arguments to the function, enclosed in parentheses and separated by commas.
- The JavaScript statements that define the function, enclosed in curly brackets, { }.

```js
function name(arg1, arg2, arg3...){
  return statement; // Can be any value
}
```

_The `return` statement tells the browser to "return the result" of the function so it is available to use. This is necessary because things defined inside functions are only available inside those functions. This is called **variable scoping**._


Below is an example of a simple function that takes two numbers as arguments and multiplies them:


```js
function multiply(num1,num2) {
  var result = num1 * num2;
  return console.log(result);
}
```

#### Calling functions

As you may have noticed, defining a function does not execute it. Defining the function simply names the function and specifies what to do when the function is called. Calling the function actually performs the specified actions with the indicated parameters. For example, since we defined a function called `multiply`, you could call it as follows:

```js
multiply(4,7);
multiply(20,20);
multiply(0.5,3);
```

#### Function scope

Variables defined inside a function cannot be accessed from anywhere outside the function, because the variable is defined only in the scope of the function. However, a function can access all variables and functions defined inside the scope in which it is defined. In other words, a function defined in the global scope can access all variables defined in the global scope. A function defined inside another function can also access all variables defined in its parent function and any other variable to which the parent function has access.

```js
// The following variables are defined in the global scope
var num1 = 20,
    num2 = 3,
    myName = "John Doe";

// This function is defined in the global scope
function multiply() {
  return num1 * num2;
}

multiply(); // Returns 60

// A nested function example
function getScore () {
  var num1 = 2,
      num2 = 3;
  
  function add() {
    return name + " scored " + (num1 + num2);
  }
  
  return add();
}

getScore(); // Returns "John Doe scored 5"
```