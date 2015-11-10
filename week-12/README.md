# Week 12: Introduction to JavaScript (Part 2)

Now that you have an introduction to the basics of values (variables), data types, and operations in JavaScript, we have the building blocks in place to start developing behavior (or interactive programs) for our sites. However, to develop behavior, we need to understand how to structure the logic, which we can do with conditional statements, functions, and loops.

We'll also discuss start diving a bit deeper in to the browser environment, and begin to learn how JavaScript plays a role in interacting with the page at hand.

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [JavaScript Files](#javascript-files)
- [Part 2: Controlling Flow](#part-2-controlling-flow)

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

This week, we'll work on controlling the flow of our code inside a JavaScript file. See the [exercise files here](exercise)

## Part 2: Controlling Flow
  - Conditional logic
  - For Loops
  - Functions