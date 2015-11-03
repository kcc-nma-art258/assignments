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
      - [Objects](#objects)
  - [Operations](#operations)
    - [Comparators](#comparators)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Getting started with JavaScript Web Programming

> _You can do pretty much anything with JavaScript. You'll start small with simple features such as carousels, image galleries, fluctuating layouts, and responses to button clicks. Eventually as you get more experienced with the language, you'll be able to create games, animated 2D and 3D graphics, full blown database-driven apps, and more!_ - [_JavaScript Basics: Mozilla Developer Network_](https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/JavaScript_basics#What_is_JavaScript_really)

To understand how to use JavaScript effectively as a tool, it requires some basic understanding of the common concepts found in most programming languages. These are things like variables, operations, functions, and conditionals (if/else); you should be familiar with some of these concepts from Sass _(which is technically a programming language which compiles to CSS)_.

Since JavaScript was developed and is primarily used for the web, there are additional features built in to the language to help with communicating to the browser and manipulate things on a web page. We'll discuss some of these advanced concepts in Part 2 & 3 of the JavaScript lectures. For now, lets take a look at the basic concepts.

## Part 1: Initial Concepts
  - Browser developer console
  - Variables
  - Operations

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
```

### Operations

#### Comparators