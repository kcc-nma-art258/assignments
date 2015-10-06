# Week 7: Enhancing Framework UI/UX

## Forms, Buttons & Utility Classes

Outside of a basic grid & typography, most frameworks also include some basic styles for our common components like forms and buttons. It's also common to include some utility classes for things that you commonly use like media queries, clear floats, et al. 

Your frameworks styling should have enough styling to look consistent across device and platform, but general enough to be used as a baseline for any site you build going forward.

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Forms](#forms)
- [Buttons](#buttons)
- [Utility Classes](#utility-classes)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Forms

Forms can be fairly complex, but setting up the styling for them doesn't have to be if you're using Sass.

Let's starting by creating a style rule selector that captures the most common form elements to apply a common baseline style.

**styles/base/_forms.scss**
```scss
input[type="email"],
input[type="number"],
input[type="search"],
input[type="text"],
input[type="tel"],
input[type="url"],
input[type="password"],
input[type="checkbox"],
input[type="radio"],
textarea,
select {
  ...
}
```

Any styles we apply here will be applied across all of our form elements we've selected. 

We'll break out some styles that are specific to each element out here shortly.

_(Also notice we didn't style certain elements like `input[type=button]` or `input[type=submit]`; these behave and appear as buttons in the UI, so we include them in our `_buttons.scss`)_

Let's first remove the default styling applied on WebKit-based mobile devices (iOS & Android)

**styles/base/_forms.scss**
```scss
input[type="email"],
input[type="number"],
input[type="search"],
input[type="text"],
input[type="tel"],
input[type="url"],
input[type="password"],
input[type="checkbox"],
input[type="radio"],
textarea,
select {
  appearance: none;
}
```

We also need to give our forms a common style for different states like `:focus` and `:active`. These states are typically styled the same.

**styles/base/_forms.scss**
```scss
input[type="email"],
input[type="number"],
input[type="search"],
input[type="text"],
input[type="tel"],
input[type="url"],
input[type="password"],
input[type="checkbox"],
input[type="radio"],
textarea,
select {
  appearance: none;

  &:focus,
  &:active {
    outline: 0;
  }
}
```

By giving those states an `outline: 0`, it removes the default blue/grey outline styling that browsers apply by default. 

Most frameworks to apply their own common styling for these states using a simple `border` or `box-shadow` styling. 

**styles/base/_forms.scss**
```scss
input[type="email"],
input[type="number"],
input[type="search"],
input[type="text"],
input[type="tel"],
input[type="url"],
input[type="password"],
input[type="checkbox"],
input[type="radio"],
textarea,
select {
  appearance: none;

  &:focus,
  &:active {
    outline: 0;
    box-shadow: 0 0 3px rgba(64, 120, 192, 0.25);
  }
}
```

From here, we can break out individual elements to give them their own unique styles for our framework.

**styles/base/_forms.scss**
```scss
input[type="email"],
input[type="number"],
input[type="search"],
input[type="text"],
input[type="tel"],
input[type="url"],
input[type="password"] {
  ...
}

input[type="checkbox"],
input[type="radio"]  {
  ...
}

input[type="checkbox"]  {
  ...
}

input[type="radio"]  {
  ...
}

textarea {
  ...
}

select {
  ...
}
```

Some common things to consider for your framework is giving your elements a default `height` or simple styling using `border` or `box-shadow`

There are also other common form elements you can also include in your framework as well, like `label`, `legend`, `fieldset`. Once you have a good set of styles for your base form, you may want to consider adding those to your project and seeing how you'd like to style them.

**References:**
- [Codepen: Form Styling Demo](http://codepen.io/micjamking/pen/7a1cbe390e4fe22315b0bd5dd08b3da2)

<!-- 
## Buttons


**References:**
- [CSS Tricks: Link Pseudo Classes in Order](https://css-tricks.com/snippets/css/link-pseudo-classes-in-order/)
- [CSS Tricks: Pseudo Class Selectors](https://css-tricks.com/pseudo-class-selectors/)

## Utility Classes

**References:**
-->