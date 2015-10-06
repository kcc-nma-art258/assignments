# Week 7: Enhancing Framework UI/UX

## Forms, Buttons & Utility Classes

Outside of a basic grid & typography, most frameworks also include some basic styles for our common components like forms and buttons. It's also common to include some utility classes for things that you commonly use like media queries, clear floats, et al. 

Your frameworks styling should have enough styling to look consistent across device and platform, but general enough to be used as a baseline for any site you build going forward.

**Table of Contents**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Forms

Forms are fairly complex, but setting up the styling for them can be done fairly simply using Sass.

Let's starting by creating a rule that captures the most common form elements to apply a common baseline style.

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

Any styles we apply here will be applied across all of our form elements we've selected. We'll break some styles that are specific to each element out here shortly.

Let's first remove the default styling applied on WebKit-based mobile devices (iOS & Android)

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

We also need to give our forms a common style 

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

**References:**

## Buttons


**References:**
- [CSS Tricks: Link Pseudo Classes in Order](https://css-tricks.com/snippets/css/link-pseudo-classes-in-order/)
- [CSS Tricks: Pseudo Class Selectors](https://css-tricks.com/pseudo-class-selectors/)

## Utility Classes

**References:**
