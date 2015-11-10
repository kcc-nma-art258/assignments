# Week 11: Introduction to JavaScript (Part 1)

Along with HTML & CSS, JavaScript (JS) is one of the three essential technologies in the web standards model. While HTML focuses on content, and CSS focuses on styling, JavaScript is a programming language used to add interactivity and special effects to your web pages. 

JavaScript is used to create a wide variety of functionality on the web, from basic form enhancements to adding dynamic content & styling (AJAX), to 2D/3D animation for games.

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Getting started with JavaScript Web Programming](#getting-started-with-javascript-web-programming)
- [Part 1: Initial Concepts](#part-1-initial-concepts)
  - [Browser developer console](#browser-developer-console)
  - [Variables](#variables)
    - [Data Types](#data-types)
      - [String](#string)
      - [Number](#number)
      - [Boolean](#boolean)
      - [Array](#array)
      - [Find Length](#find-length)
      - [Add to end of Array](#add-to-end-of-array)
      - [Remove from the end of an Array](#remove-from-the-end-of-an-array)
      - [Add to the front of an Array](#add-to-the-front-of-an-array)
      - [Remove from the front of an Array](#remove-from-the-front-of-an-array)
      - [Find the index of an item in the Array](#find-the-index-of-an-item-in-the-array)
      - [Remove an item by Index Position](#remove-an-item-by-index-position)
      - [Copy an Array](#copy-an-array)
      - [Objects](#objects)
  - [Operators](#operators)
    - [Add/concatenation](#addconcatenation)
    - [Subtract, Multiply, Divide](#subtract-multiply-divide)
    - [Assignment](#assignment)
    - [Identity (equals)](#identity-equals)
    - [Negation, Not equal](#negation-not-equal)
    - [Comparators](#comparators)
      - [Greater than](#greater-than)
      - [Greater than or equal](#greater-than-or-equal)
      - [Less than](#less-than)
      - [Less than or equal](#less-than-or-equal)
    - [Order of Operations: P.E.M.D.A.S.](#order-of-operations-pemdas)
  - [console.log](#consolelog)
  - [Keywords and reserved words](#keywords-and-reserved-words)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Getting started with JavaScript Web Programming

> _You can do pretty much anything with JavaScript. You'll start small with simple features such as carousels, image galleries, fluctuating layouts, and responses to button clicks. Eventually as you get more experienced with the language, you'll be able to create games, animated 2D and 3D graphics, full blown database-driven apps, and more!_ - [_JavaScript Basics: Mozilla Developer Network_](https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/JavaScript_basics#What_is_JavaScript_really)

To understand how to use JavaScript effectively as a tool, it requires some basic understanding of the common concepts found in most programming languages. These are things like variables, operations, functions, and conditionals (if/else); you should be familiar with some of these concepts from Sass _(which is technically a programming language which compiles to CSS)_.

Since JavaScript was developed and is primarily used for the web, there are additional features built in to the language to help with communicating to the browser and manipulate things on a web page. We'll discuss some of these advanced concepts in Part 2 & 3 of the JavaScript lectures. For now, lets take a look at the basic concepts.

## Part 1: Initial Concepts
  - Browser developer console
  - Variables
  - Operators

### Browser developer console

The browser developer console, or _console_ for short, is a JavaScript prompt that is used to display things returned from your code. Your JavaScript files can ouput directly to the console, or you can interact within the console to perform small JavaScript operations.

**Ref:**
- [Discover Browser Developer Consoles](https://developer.mozilla.org/en-US/Learn/Discover_browser_developer_tools)

### Variables

Variables are containers that you can store values in. You start by declaring a variable with the var keyword, followed by any name you want to call it.

```js
var foo;

foo = 7;
```

Some things to note about JS variables:
 - All statements in JavaScript must end with a semi-colon, to indicate that this is where the statement ends. If you don't include these, you can get unexpected results.
 - You can name a variable nearly anything, but there are some name restrictions
 - JavaScript is case sensitive — myVariable is a different variable to myvariable. If you are getting problems in your code, check the casing!

You can assign a variable after declaring it, like above, or you can assign the variable during declaration.

```js
var foo = 7;

foo; // 7
```
Variables can store a few other things besides just numbers and strings, and each with their own data type.

#### Data Types

##### String

A string of text. To signify that the variable is a string, you should enclose it in quote marks.

```js
var foo = 'Yo';

foo; // Yo
```

##### Number

A number. Numbers don't have quotes around them.

```js
var foo = 7;

foo; // 7
```

##### Boolean

A True/False value. The words true and false are special keywords in JS, and don't need quotes.

```js
var foo = true;

foo; // true
```

##### Array

A structure that allows you to store multiple values in one single reference.

```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];

foo; // ['Tokyo', 'Honolulu', 'San Francisco']

foo[2]; // 'San Francisco'
```

JavaScript arrays are zero-indexed: the first element of an array is at index 0, and the last element is at the index equal to the value of the array's length property minus 1.


Arrays also have additional properties which can be accessed using _JavaScript Object dot-notation_.

##### Find Length
```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];

foo.length; // 3

foo[foo.length - 1]; // 'San Francisco'
```

##### Add to end of Array
```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];

foo.push('New York');

foo; // ['Tokyo', 'Honolulu', 'San Francisco', 'New York']
```

##### Remove from the end of an Array
```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];
var last = foo.pop(); // remove 'San Francisco' (from the end)

last; // 'San Francisco'
foo; // ['Tokyo', 'Honolulu']
```

##### Add to the front of an Array
```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];
foo.unshift('Sydney') // add to the front

foo; // ['Sydney', 'Tokyo', 'Honolulu', 'San Francisco']
```

##### Remove from the front of an Array
```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];
var first = foo.shift(); // remove 'Tokyo' (from the front)

first; // 'Tokyo'
foo; // ['Honolulu', 'San Francisco']
```

##### Find the index of an item in the Array
```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];
var pos = foo.indexOf('Honolulu');
pos; // 1 (Remember, zero-based index)
```

##### Remove an item by Index Position

```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];
var pos = foo.indexOf('Honolulu');
var removedItem = foo.splice(pos, 1); 

removedItem; // 'Honolulu'
foo; // ['Tokyo', 'San Francisco']
```

##### Copy an Array

```js
var foo = ['Tokyo', 'Honolulu', 'San Francisco'];
var shallowCopy = foo.slice(); // this is how to make a copy

shallowCopy; // ['Tokyo', 'Honolulu', 'San Francisco']
foo; // ['Tokyo', 'Honolulu', 'San Francisco']
```


##### Objects

Basically, anything. Everything in JavaScript is an object, and can be stored in a variable. Keep this in mind as you learn.

```js
var foo = {
   cities: ['Tokyo', 'Honolulu', 'San Francisco'],
   currentlyInCity: true,
   friendsInCities: 7 
};

foo.cities; // ['Tokyo', 'Honolulu', 'San Francisco']
foo.currentlyInCity; // true
foo.friendsInCities; // 7
```

An object is a list of zero or more pairs of property names and associated values of an object, enclosed in curly braces ({}).

### Operators

An operator is a mathematical symbol that produces a result based on two values (or variables). Below are some of the simplest operators, along with some examples to try out in the JavaScript console.

#### Add/concatenation
- **Symbol(s):** `+`
- Used to add two numbers together, or glue two strings together.

**Example:**
```js
6 + 9; // 15
"Hello " + "world!"; // "Hello world!"
```

#### Subtract, Multiply, Divide
- **Symbol(s):** `-, *, /`
- These do what you'd expect them to do in basic math.

**Example:**
```js
9 - 3; // 6
8 * 2; // 16
9 / 3; // 3
```

#### Assignment
- **Symbol(s):** `=`
- You've seen this already: it assigns a value to a variable.

**Example:**
```js
var myVariable = 'Bob';
myVariable; // 'Bob';
```

#### Identity (equals)
- **Symbol(s):** `===`
- Does a test to see if two values are equal to one another, and returns a true/false (Boolean) result.

**Example:**
```js
var myVariable = 3;
myVariable === 4; // false
```
#### Negation, Not equal
- **Symbol(s):** `!, !==`
- Returns the logically opposite value of what it preceeds; it turns  a true into a false, etc. When it is used alongside the Equality operator, the negation operator tests whether two values are not equal.

**Example:**
```js
// Negate, or return the opposite of, the value
var myVariable = 3;
!(myVariable === 3); // false

// Test whether "myVariable is NOT equal to 3"
var myVariable = 3;
myVariable !== 3; // false
```

#### Comparators

##### Greater than
- **Symbol(s):** `>`
- The greater than operator returns true if the left operand is greater than the right operand.

**Example:**
```js
4 > 3; // true
```

##### Greater than or equal
- **Symbol(s):** `>=`
- The greater than or equal operator returns true if the left operand is greater than or equal to the right operand.

**Example:**
```js
4 >= 3; // true
3 >= 3; // true
```

##### Less than
- **Symbol(s):** `<`
- The less than operator returns true if the left operand is less than the right operand.

**Example:**
```js
3 < 4 // true
```

##### Less than or equal
- **Symbol(s):** `<=`
- The less than or equal operator returns true if the left operand is less than or equal to the right operand.

**Example:**
```js
3 <= 4 // true
```

#### Order of Operations: P.E.M.D.A.S.
- Group expressions in JavaScript

**Example:**
```js
(5 + 7) * 3 // 36
```

### console.log

When you're actually working with JavaScript, you'll be most likely writing it within and linking it on your page. In this instance, it's helpful to ouput content to the console to understand whats going on in your script or program. This is where console.log comes in.
- In Chrome DevTools, select the `Sources > Snippets` tab, right-click inside of the sidebar, and create a new file called `ex-1.js`

**Example:**
```js
console.log('yo!');
```

### Keywords and reserved words

Words with a special meaning, such as var, are keywords, and they may not be used as variable names. There are also a number of words that are “reserved for use” in future versions of JavaScript. These are also officially not allowed to be used as variable names, though some JavaScript environments do allow them. The full list of keywords and reserved words is rather long.

```js
break case catch class const continue debugger
default delete do else enum export extends false
finally for function if implements import in
instanceof interface let new null package private
protected public return static super switch this
throw true try typeof var void while with yield
```
Don’t worry about memorizing these, but remember that this might be the problem when a variable definition does not work as expected.