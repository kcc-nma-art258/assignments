# Week 13: Introduction to JavaScript (Part 3)

We've spent the last two weeks wrapping our heads around basic programming concepts. This week we'll focus on JavaScript's role in the browser and how we can use the previous concepts we discussed, along with browser specific features, like the _Document Object Model (DOM)_, Events, and Storage to start building functionality in our web pages. 

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## The Document Object Model (DOM)

When you open a web page in your browser, the browser retrieves the page’s HTML text and parses it. The browser builds up a _model_ of the document’s structure and then uses this model to draw the page on the screen.

This _model_ of the document is one of the browser features that JavaScript has access to: you can read from the model and also change it. The DOM acts as a live data structure: when it is modified, the page on the screen is updated to reflect the changes.

**Example: `index.html`**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>My Manini Website</title>
  </head>
  <body>
    <h1 id="title">My home page</h1>
    <p>Hello, I am Mike and this is my home page.</p>
    <p class="description">I also teach KCC ART258! Check it out
      <a href="https://github.com/kcc-nma-art258">here</a>.</p>
  </body>
</html>
```

**This page has the following _DOM_ structure:**

![DOM image](images/dom-images.png)

For each box, there is an **object**, which we can interact with to find out things such as what HTML tag it represents and which boxes and text it contains. This representation is called the _Document Object Model_, or DOM for short.

### Finding Elements in the DOM

In JavaScript, there is a global variable called `document`, which gives us access to the DOM of an HTML page. The `document` object also contains a number of _methods_, or properties that refer to functions (like `console.log()`), which we can use to access and manipulate properties of the elements.

For example, if we wanted to find the `href` value of the link in our above example, we could do the following:

```js
var link = document.querySelectorAll('a')[0];

console.log(link); // <a href="https://github.com/kcc-nma-art258">here</a>
console.log(link.href); // https://github.com/kcc-nma-art258
```

`querySelectorAll` is a method available to all element nodes, which searches within the element (in our case `document`) and finds an element using any valid CSS selector. 

We can access each element in the `body` of our document like so:

```js
var title = document.querySelectorAll('#title')[0];
var intro = document.querySelectorAll('p')[0];
var descr = document.querySelectorAll('.description')[0];
var link  = document.querySelectorAll('a:link')[0];

console.log(title.innerHTML); // My home page
console.log(intro.innerHTML); // Hello, I am Mike and this is my home page.
console.log(descr.innerHTML); // I also teach KCC ART258! Check it out <a href="https://github.com/kcc-nma-art258">here</a>.
console.log(link.innerHTML); // here
```

As you can see in the above, we can display the inner content of each element using the `element.innerHTML` property. Note that if the HTML element contains further nested HTML, `element.innerHTML` will output the nested HTML elements as well.

**So, how do we display just the text?**

```js
console.log(descr.textContent);
```

There are quite a few properties and _methods_ available for elements, so you can refer to the below resources to learn more about what the properties available

**Resources:**
- [Element - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element)

### Manipulating the DOM
