# Week 7: Enhancing Framework UI/UX

## Forms, Buttons & Utility Classes

Outside of a basic grid & typography, most frameworks also include some basic styles for our common components like forms and buttons. It's also common to include some utility classes for things that you commonly use like media queries, clear floats, et al. 

Your frameworks styling should have enough styling to look consistent across device and platform, but general enough to be used as a baseline for any site you build going forward.

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Forms](#forms)
- [Buttons](#buttons)
  - [States](#states)
- [Utility Classes](#utility-classes)
- [General](#general)

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

## Buttons

For our button styles, we want to create a general styling to serve as a good baseline to further create any polished button style we may need in the future.

Similar to our forms, we'll set up a base style rule that will target all of our button styles and then apply specific button type styles later.

**styles/modules/_buttons.scss**

```scss
.button,
button,
input[type="submit"],
input[type="reset"],
input[type="button"] {
  ...
}
```

Noticed that we also included a `.button` class; this will come in handy when you want to style anchor tags (`<a>`) to look like buttons.

Similar to the form input types, we want to first remove the default styling Webkit _(Safari/Chrome; iOS/Android)_ browsers apply to buttons

**styles/modules/_buttons.scss**

```scss
.button,
button,
input[type="submit"],
input[type="reset"],
input[type="button"] {
  appearance: none;
}
```

This removes the browser chrome, but there's still some styles that could be removed like the default border and background.

**styles/modules/_buttons.scss**

```scss
.button,
button,
input[type="submit"],
input[type="reset"],
input[type="button"] {
  appearance: none;
  background-color: transparent;
  border: 0 none;
}
```

Let's add a few more style declarations to make our buttons consistent, across the board.

**styles/modules/_buttons.scss**

```scss
.button,
button,
input[type="submit"],
input[type="reset"],
input[type="button"] {
  appearance: none;
  background-color: transparent;
  border: 0 none;
  
  display: inline-block; // Make display properties consistent across the board
  text-decoration: none; // Remove underline for anchor buttons
  color: inherit;        // Inherit the default color (ie. black)
  padding: 0.5em 1em;
  margin-bottom: 0.5em;
  background-color: #DEDEDE;
  border-radius: 2px;
}
```

### States

The most important thing a button does is provide an action for users to take on your site. We can provide visual feedback while the button is in different states to let users know what's going on.

**styles/modules/_buttons.scss**

```scss
.button,
button,
input[type="submit"],
input[type="reset"],
input[type="button"] {
  appearance: none;
  background-color: transparent;
  border: 0 none;
  
  display: inline-block; // Make display properties consistent across the board
  text-decoration: none; // Remove underline for anchor buttons
  color: inherit;        // Inherit the default color (ie. black)
  padding: 0.5em 1em;
  margin-bottom: 0.5em;
  background-color: #DEDEDE;
  border-radius: 2px;

  &:hover {
    background-color: #CACACA;          
  }

  &:focus,
  &:active {
    outline: none;
    box-shadow: 0 0 1px 3px rgba(76, 130, 246, 0.5);
  }
}
```

There's a lot of interesting things you can do with buttons, but your frameworks defaults should be simple enough to cover your most common use cases. For example, you could create additional button classess for primary and secondary buttons, or create default styles for social media buttons.

**References:**
- [Codepen: Button Demo](http://codepen.io/micjamking/pen/b728e3e926ffa8fe53b8a3ddc3f52b29)
- [CSS Tricks: Pseudo Class Selectors](https://css-tricks.com/pseudo-class-selectors/)
- [Codepen: CSS Button Demos](http://codepen.io/search/pens?q=buttons&type=type-pens)

## Utility Classes

Outside of our grid, typography, form, and button styles, sometimes you need helpers for solving common problems in your design. A good example is like our `.cf` mixin in Sass to apply a clear fix for floats. We call these types of helpers _"utilities"_ or _"utility classes"_, because they serve more of a utility purpose when used in your styles.

When you're writing Sass, your utilities are most likely stored in variables, mixins and functions to keep your code DRY. So our utilities can be broken down in to multiple files to make things more manageable and efficient. However, if certain utilities depend on one another, you need to pay attention to the load order in your main `style.scss` file.

Let's start with a few common variables...

**styles/base/_variables.scss**

```scss
// Variables
$base-font-size: 16px;
$line-height: 1.5;
$serif: 'Baskerville', Georgia, Palatino, serif;
$sans-serif: 'Helvetica Neue', Helvetica, Arial, sans-serif;
```

...and our clearfix mixin

**styles/base/_mixins.scss**

```scss
// Mixins
@mixin cf {
  &:before,
  &:after {
    content: "";
    display: table;
 }

  &:after {
    clear: both;
  }
}
```

After my base variables and mixins have been setup, I usually starting figuring out my media queries while I'm developing my grid. By storing your media queries in variables, it makes it easier to reuse them throughout your styles without error.

**styles/base/_media-queries.scss**
```scss
/**
 * Media Queries
 *
 * NOTE: "Relative units in media queries are based 
 * on the initial value, which means that units are 
 * never based on results of declarations"
 * http://www.w3.org/TR/css3-mediaqueries/#units
 *
 * usage: @media #{$medium-screen} { ... }
 */
$small-screen:  'only screen';
$medium-screen: 'only screen and (min-width: em-calc(640px, 16px))';
$large-screen:  'only screen and (min-width: em-calc(1024px, 16px))';
$xlarge-screen: 'only screen and (min-width: em-calc(1440px, 16px))';
```

If you noticed above, I'm setting my `min-width` value using a function. This function is a simple Sass em calculator that can be use throughout our styles to help with converting pixels to em/rem.

**styles/base/_functions.scss**
```scss
// Functions

// rem/em Calculator (ie. em-calc(32px, 16px, 'rem'))
@function em-calc($target, $context: $base-font, $unit: 'rem'){
  // target / context = result (defaults to rem's)
  @return #{$target/$context} + $unit;
}
```
You can also add utility classes for common tasks like floating (ie. `.float-right`), text-aligning (ie. '.align-center') and show/hiding elements (ie. '.show'), but I try to create as few of these as possible because they have the potential to litter up our HTML (WET). However these can be very helpful for prototyping and getting ideas out quickly in code, so its up to you how much styling and classes your framework provides.

**References:**
- [Sitepoint: Using Helper Classes to DRY up CSS](http://www.sitepoint.com/using-helper-classes-dry-scale-css/)
- [Foundation Framework: Utilities](http://foundation.zurb.com/docs/utility-classes.html)

## General

CSS frameworks can be very simple, like [Skeleton](http://getskeleton.com/) (and the one you're making now) or really complex with a lot of components like [Bootstrap](http://getbootstrap.com/). The most important thing that a custom CSS framework does is **work for you**. So if something is not working, doesn't belong or make sense in your project, don't use it. However, if you find yourself repeating the same tasks over and over again, think about how you may want to simplify it so that it can be reused again in later projects.