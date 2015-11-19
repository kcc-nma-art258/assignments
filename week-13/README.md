# Week 13: Introduction to JavaScript (Part 3)

We've spent the last two weeks wrapping our heads around basic programming concepts. This week we'll focus on JavaScript's role in the browser and how we can use the previous concepts we discussed, along with browser specific features, like the _Document Object Model (DOM)_, Events, and Storage to start building functionality in our web pages. 

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


  - [The Document Object Model (DOM)](#the-document-object-model-dom)
    - [Finding Elements](#finding-elements)
    - [Manipulating Elements](#manipulating-elements)
      - [Hide element](#hide-element)
      - [Show element](#show-element)
      - [Add (inline) CSS styles](#add-inline-css-styles)
      - [Get (stylesheet) CSS styles](#get-stylesheet-css-styles)
      - [Get Element Width/Height](#get-element-widthheight)
      - [Get Element Position (relative to viewport)](#get-element-position-relative-to-viewport)
      - [Add class to element](#add-class-to-element)
      - [Remove class from element](#remove-class-from-element)
      - [Has Class (returns true or false)](#has-class-returns-true-or-false)
      - [Get Text](#get-text)
      - [Set Text](#set-text)
      - [Get HTML](#get-html)
      - [Set HTML](#set-html)
      - [Get Attribute](#get-attribute)
      - [Set Attribute](#set-attribute)
      - [Create new element](#create-new-element)
      - [Create content (text)](#create-content-text)
      - [Append element (insert at end)](#append-element-insert-at-end)
      - [Prepend element (insert at beginning)](#prepend-element-insert-at-beginning)
      - [Remove element](#remove-element)
  - [Events](#events)
    - [Event Object](#event-object)
    - [Mouse Events](#mouse-events)
    - [Keyboard Events](#keyboard-events)
    - [Scroll Events](#scroll-events)
    - [Timed Events](#timed-events)
  - [Storage](#storage)
    - [`localstorage` property](#localstorage-property)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## The Document Object Model (DOM)

When you open a web page in your browser, the browser retrieves the page’s HTML text and parses it. The browser builds up a _model_ of the document’s structure and then uses this model to draw the page on the screen.

This _model_ of the document is one of the browser features that JavaScript has access to: you can read from the model and also change it. The DOM acts as a live data structure: when it is modified, the page on the screen is updated to reflect the changes.

**Example: `index.html`**

```html
<!DOCTYPE html>
<html lang='en'>
  <head>
    <title>My Manini Website</title>
  </head>
  <body>
    <h1 id='title'>My home page</h1>
    <p>Hello, I am Mike and this is my home page.</p>
    <p class='description'>I also teach KCC ART258! Check it out
      <a href='https://github.com/kcc-nma-art258'>here</a>.</p>
  </body>
</html>
```

**This page has the following _DOM_ structure:**

![DOM image](images/dom-images.png)

For each box, there is an **object**, which we can interact with to find out things such as what HTML tag it represents and which boxes and text it contains. This representation is called the _Document Object Model_, or DOM for short.

In JavaScript, the DOM is typically referred to as a tree structure, because every object in the node has a parent/child/sibling relationship with the other nodes, similar to a _family tree_. 

In our example, our `h1` element is a sibling of our `p` elements, which are children of our `body` element, which is a child of our `html` element. Remembering this structure will be helpful when writing JavaScript and interacting with the DOM, because a lot of common tasks that you perform with JavaScript will be easier with this understanding.

### Finding Elements

In JavaScript, there is a global variable called `document`, which gives us access to the DOM of an HTML page. The `document` object also contains a number of _methods_, or properties that refer to functions (like `console.log()`), which we can use to access and manipulate properties of the elements.

For example, if we wanted to find the `href` value of the link in our above example, we could do the following:

```js
var link = document.querySelectorAll('a')[0];

console.log(link); // <a href='https://github.com/kcc-nma-art258'>here</a>
console.log(link.href); // https://github.com/kcc-nma-art258
```

`querySelectorAll` is a method available to all element nodes, which searches within the element (in our case `document`) and finds an element using any valid CSS selector. The `querySelectorAll` method returns an array of elements which match the query. _(If there is a single match, it will be available in the zero position of the returned array)_

We can access each element in the `body` of our document like so:

```js
var title = document.querySelectorAll('#title')[0];
var intro = document.querySelectorAll('p')[0];
var descr = document.querySelectorAll('.description')[0];
var link  = document.querySelectorAll('a:link')[0];

console.log(title.innerHTML); // My home page
console.log(intro.innerHTML); // Hello, I am Mike and this is my home page.
console.log(descr.innerHTML); // I also teach KCC ART258! Check it out <a href='https://github.com/kcc-nma-art258'>here</a>.
console.log(link.innerHTML); // here
```

As you can see in the above, we can display the inner content of each element using the `element.innerHTML` property. Note that if the HTML element contains further nested HTML, `element.innerHTML` will output the nested HTML elements as well.

**So, how do we display just the text?**

```js
console.log(descr.textContent);
```

There are quite a few properties and _methods_ available for elements, so you can refer to the below resources to learn more about what the properties available

**Resources:**
- [Document | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document)
- [HTMLElement | MDN](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  - Inherits properties from [Element](https://developer.mozilla.org/en-US/docs/Web/API/Element)

### Manipulating Elements

Given the following HTML elements and JS variables...

```html
<header class='main-header'>
  <h1 id='title'>My Company Name</h1>
</header>
```

```js
var el     = document.querySelectorAll('#title')[0];
var parent = el.parentNode; // This will grab the immediate parent element of `el`
```

Below is a list of common tasks that you may like to perform using JavaScript:

#### Hide element

```js
el.style.display = 'none';
```

#### Show element

```js
el.style.display = '';
```

#### Add (inline) CSS styles

```js
el.style.borderColor = 'red';
```
_(CSS properties with hyphens like `border-color` are camelCase when accessing them in JavaScript.)_

#### Get (stylesheet) CSS styles

```js
getComputedStyle(el).getPropertyValue('height');
```

#### Get Element Width/Height

```js
el.offsetHeight;
el.offsetWidth;
```

#### Get Element Position (relative to viewport)

```js
el.getBoundingClientRect();
```

#### Add class to element

```js
var className = 'my-new-class';
// IE 10
if (el.classList){
  el.classList.add(className);
} else {
// IE 8+
  el.className += ' ' + className;
}
```

#### Remove class from element

```js
var className = 'my-new-class';
// IE 10
if (el.classList){
  el.classList.remove(className);
} else {
// IE 8+
  el.className = el.className.replace(new RegExp('(^|\\b)' + className.split(' ').join('|') + '(\\b|$)', 'gi'), ' ');
}
```

#### Has Class (returns true or false)

```js
var className = 'my-new-class';
// IE 10
if (el.classList){
  el.classList.contains(className);
} else {
// IE 8+
  new RegExp('(^| )' + className + '( |$)', 'gi').test(el.className);
}
```

#### Get Text

```js
el.textContent;
```

#### Set Text

```js
el.textContent = 'My New Company Name';
```

#### Get HTML

```js
parent.innerHTML;
```

#### Set HTML

```js
parent.innerHTML = '<h2 class='subtitle'>My Other Company Name</h2>';
```

#### Get Attribute

```js
el.getAttribute('id'); // title
```

#### Set Attribute

```js
el.setAttribute('alt', 'This is My Heading');
```

You can also create new elements and dynamically insert and remove them from the page.

#### Create new element

```js
var newDiv = document.createElement('div'); 
```

#### Create content (text)

```js
var newContent = document.createTextNode('Hi there and greetings!');
```

#### Append element (insert at end)

```js
newDiv.appendChild(newContent); // Adds content to newly created div
parent.appendChild(newDiv); // Adds newDiv to DOM (live HTML page), after our h1.title
```

#### Prepend element (insert at beginning)

```js
parent.insertBefore(newDiv, parent.firstChild); // Adds newDiv to DOM, before our h1.title
```

#### Remove element 

```js
parent.removeChild(el);
// or if you don't know the parent element
el.parentNode.removeChild(el);
```

## Events

Sometimes we will want to perform an action like adding a class to an element, but only during some type of user interaction, ie. a touch-tap or mouse-click, while scrolling, or when a user submits a form. This requires our code to _react_ to events that occur during human-computer interaction. 

Luckily, browsers a built-in waying of handling this by allowing us to register functions as _listeners_ for specific events.

**Example: `index.html`**
```html
<button>Click me</button>
```

**Example: `script.js`**
```js
var button = document.querySelectorAll('button')[0];

function clickMeListener(){
  console.log('Yo!');
}

button.addEventListener('click', clickMeListener);
```

_(Now try clicking the button and opening up you console.)_

The example attaches a `click` event listener function to the button node, thus, clicks on the button cause that listener function to run. Notice that we only refer to the listener function by name `clickMeListener`, rather than calling it like we would a normal function with parenthesis at the end (ie. `clickMeListener()`).

The `addEventListener` method allows you to add any number of handlers to an element, as well as listen for multiple types of events, even ones you create yourself.

Common events include:

**Mouse Events**
 - `click`: The user clicks an HTML element
 - `mouseover`: The user moves the mouse over an HTML element
 - `mouseout`: The user moves the mouse away from an HTML element

**Touch Events** 	 
 - `touchstart`: The event occurs when a finger is placed on a touch screen 
 - `touchmove`: The event occurs when a finger is dragged across the screen
 - `touchend`: The event occurs when a finger is removed from a touch screen

**Keyboard Events**
 - `keydown`: The event occurs _while_ the user is pressing a key (continually fires)
 - `keypress`: The event occurs _when_ the user presses a key (fires once)
 - `keyup`: The event occurs when the user releases a key

**Element/Form Events** 
 - `focus`: The event occurs when an element gets focus
 - `blur`: The event occurs when an element loses focus
 - `change`: The event occurs when the content of a form element, the selection, or the checked state have changed (for `<input>`, `<select>`, and `<textarea>`)
 - `submit`: The event occurs when a form is submitted 

**Browser Events**
 - `load`: The browser has finished loading the page
 - `resize`: The event occurs when the document view is resized
 - `scroll`: The event occurs when an element's scrollbar is being scrolled

**Resources:**
- [Events | MDN](https://developer.mozilla.org/en-US/docs/Web/Events)
- [HTML DOM Events | W3Schools](http://www.w3schools.com/jsref/dom_obj_event.asp)

### Event Object

Though we have ignored it in the previous example, event listener functions are passed an argument: the event object. This object gives us additional information about the event. For example, if we want to know which mouse button was pressed, we can look at the event object’s `which` property.

```js
var button = document.querySelectorAll('button')[0];

function clickMeListener(event) {
  if (event.which == 1) {
    console.log('Left button');
  } else if (event.which == 2) {
    console.log('Middle button');
  } else if (event.which == 3) {
    console.log('Right button');
  }
}

button.addEventListener('click', clickMeListener);
```
The information stored in an event object will differ depending on the type of event.

### Mouse Events

Based on what we've just learned, we can create a primitive drawing program. While moving your mouse over the document, it adds a dot under your mouse pointer.

**Example: style.css**
```css
html,
body {
  width: 100%;
  height: 100%;
}

.dot {
  height: 8px; 
  width: 8px;
  border-radius: 4px; /* rounds corners */
  background: blue;
  position: absolute;
}
```

**Example: script.js**
```js
function drawDotListener(event) {
  // Create new div element
  var dot        = document.createElement('div');
  
  // Give it a class of dot
  // and set it's positioning properties
  dot.className  = 'dot';
  dot.style.left = (event.pageX - 4) + 'px';
  dot.style.top  = (event.pageY - 4) + 'px';
  
  // Append the dot to the document
  document.body.appendChild(dot);
}

window.addEventListener('mouseover', drawDotListener);
```
As mentioned earlier, every event object has it's own properties; in this case we're working with the _MouseEvent object_, which contains several properties related to coordinates from the mouse interaction.

The `clientX` and `clientY` properties provide relative coordinates to the part of the document that is currently scrolled into view. These can be useful when comparing mouse coordinates with the coordinates returned by `getBoundingClientRect`, which also returns viewport-relative coordinates.

**Resources:**
- [MouseEvent | MDN](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent)

### Keyboard Events

When a key on the keyboard is pressed, your browser fires a `keydown` event. When it is released, a `keyup` event fires.

```js
function keyDownListener(event) {
  if (event.keyCode == 86){
    document.body.style.background = 'violet';
  }
}

function keyUpListener(event) {
  if (event.keyCode == 86){
    document.body.style.background = '';
  }
}

window.addEventListener('keydown', keyDownListener);
window.addEventListener('keyup', keyUpListener);
```

Notice a couple of things in the previous example:
- We use the `keyCode` property of the event object to identify which key is being pressed or released. Unfortunately, it’s not always obvious how to translate the numeric key code to an actual key. Will show how to figure this out here shortly.
- We add the event listener to the `window` rather than a specific HTML element like the previous examples. This is because we want to listen for keyboard interactions for the entire page.

For letter and number keys, the associated key code will be the Unicode character code associated with the (uppercase) letter or number printed on the key.

An easy way to figure out what key you need is to create a key event listener that console.logs the key codes it gets and press the key you are interested in.

```js
function keyPressListener(event) {
  console.log(event.keyCode);
}

window.addEventListener('keypress', keyPressListener);
```

### Scroll Events

Whenever an element is scrolled, a `scroll` event fires on it. This has various uses, such as knowing what the user is currently looking at or showing some indication of progress (by highlighting part of a table of contents or showing a page number). The following example draws a progress bar in the top-right corner of the document and updates it to fill up as you scroll down:

**Example: index.html**
```html
<div class='progress'><div></div></div>
<p>Scroll me...</p>
```

**Example: style.css**
```css
body {
  height: 2000px;
}

.progress {
  border: 1px solid blue;
  width: 100px;
  position: fixed;
  top: 10px; right: 10px;
}
.progress > div {
  height: 12px;
  background: blue;
  width: 0%;
}
```

**Example: script.js**
```js
var bar = document.querySelectorAll('.progress > div')[0];

function scrollProgressListener() {
  // Get the difference in height from the entire document and the window
  var max = document.body.scrollHeight - window.innerHeight;
  
  // Convert the difference to a percentage
  var percent = (window.pageYOffset / max) * 100;
  
  // Set the percentage as a style on progress element
  bar.style.width = percent + '%';
}

window.addEventListener('scroll', scrollProgressListener);
```

### Timed Events

Sometimes you just want a function to fire after a certain amount of time has passed. `setTimeout` is a globally available function used to schedules other functions to be called later. Below is an example, turning a page from blue to yellow after two seconds:

```js
document.body.style.background = "blue";

function changeColor() {
  document.body.style.background = "yellow";
}

setTimeout(changeColor, 2000);
```

Instead of calling the function immediately (ie. `changeColor()`), it waits for a given amount of milliseconds (ie. `2000`).

## Storage

Depending on the intended behavior of the site or app we're developing, we occasionally need to store some information so we can access it again later.

The Web Storage API (or Web/HTML5 Storage) provides mechanisms so browsers can store name/value pairs of information similar to one big object.

### `localstorage` property

The `localStorage` property allows you to access a local storage object. `localStorage` has no expiration time, so data stored persists even when the browser is closed. However it can be emptied manually by the user whenever the user clear's their browser cache.

**Example: index.html**
```html
<h1 class='username'></h1>
```

**Example: script.js**
```js
var username = document.querySelectorAll('username')[0];

// Save data to the current local store
localStorage.setItem('username', 'John');

// Access some stored data
username.innerHTML = localStorage.getItem('username');
```

First, we create a `localStorage` name/value pair with name='username' and value='John'. Then we retrieve the value of 'username' and insert it into the element with the class `.username`.