# Week 4: CSS Architecture & Frameworks

Replicating visual designs perfectly in code is just one side and challenge of writing CSS. As you begin to write CSS for larger sites and applications, additional considerations need to be taken in to account, including:

- Is the code readable/understandable?
- Is the code easy to change or extend?
- Is the code well decoupled?
- Will the code scale?

By focusing on good CSS architecture, we can answer yes to the above questions and have confidence that our code will stand the test of time.

**Table of Contents**
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Structuring your stylesheets](#structuring-your-stylesheets)
  - [Folder structure](#folder-structure)
    - [Base](#base)
    - [Layout](#layout)
    - [Modules](#modules)
    - [Pages](#pages)
  - [Connecting them all together](#connecting-them-all-together)
- [General guidelines for CSS architecture:](#general-guidelines-for-css-architecture)
- [Resources](#resources)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Structuring your stylesheets

One of the nice things about Sass is that it allows for a more sophisticated project structure than CSS out-of-the-box. Sass extends the [`@import`](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#import) rule to allow import of SCSS and Sass files. Unlike the normal `@import` rule, in Sass, the imported files will be merged into a single CSS output file.

So lets take a look at how we can use Sass & `@import` to structure our project:

### Folder structure

First thing is to setup your folder structure; we'll explain what each of these mean here shortly.

```
styles/
|
|-- base/
|-- layout/
|-- modules/
|-- pages/
|   
|-- reset.css
|-- style.css
|-- style.css.map
|-- style.scss
```

As we move through each section, we'll create a partial `.scss` file, with just the styles we need, and then in the end, we'll include them all back together.

#### Base
`base/` is where all of your foundational styling is going to go. Typically in this folder, you'll find a reset, typography styles, and handy sass utilities like variables, functions, and mixins.

Let's move our `reset.css` in to our `base/` and then rename it `_reset.scss` (we'll explain what the underscore at the beginning here means at the end). Let's also go ahead and remove it from our HTML.

Create a new file called `_utilities.scss` and move all of the variables and @mixins (not `@extend`) from `style.scss` here.

Now our folder structure should look like this:

```
styles/
|
|-- base/
|   |-- _reset.scss
|   |-- _utilities.scss
|
|-- layout/
|-- modules/
|-- pages/
|   
|-- style.css
|-- style.css.map
|-- style.scss
```

Specifically, the new files we added were:
- `_reset.scss`
- `_utilities.scss`

#### Layout
The `layout/` directory (sometimes called `partials`) is where the styles for our large sections of layout _which are shared across the site_ will go. This is where our grid as well as the common areas live, like our header, footer, etc.

Let's create the following files and move our styles from `style.scss` to their respective place:

- `_header.scss`
- `_footer.scss`
- `_grid.scss`

*(We haven't created a grid yet, so for now we can just move our `.container` class in to it)*

Now our folder structure should look like this:

```
styles/
|
|-- base/
|   |-- _reset.scss
|   |-- _utilities.scss
|
|-- layout/
|   |-- _header.scss
|   |-- _footer.scss
|   |-- _grid.scss
|
|-- modules/
|-- pages/
|   
|-- style.css
|-- style.css.map
|-- style.scss
```

Our `style.scss` should also be getting smaller...

#### Modules
The `modules/` directory (sometimes called `components/`) is for the smaller portions of the design which make up the major layout sections. While `layout/` is kind of _macro_ (defining the global wireframe), `modules/` is more _micro_. This is usually where most of the files live, since your whole site _should_ be made up of small modules.

For our site, let's create the following modules and move their respective styles in to it from the `style.scss`:
- `_hero.scss`
- `_search-bar.scss`
- `_site-info.scss`

Now our folder structure should look like this:

```
styles/
|
|-- base/
|   |-- _reset.scss
|   |-- _utilities.scss
|
|-- layout/
|   |-- _header.scss
|   |-- _footer.scss
|   |-- _grid.scss
|
|-- modules/
|   |-- _hero.scss
|   |-- _search-bar.scss
|   |-- _site-info.scss
|   
|-- pages/
|
|-- style.css
|-- style.css.map
|-- style.scss
```

...and our `style.scss` should be empty now, but there is still one more folder to share.

#### Pages
The `pages/` folder is where all of the page specific styles go that don't make up the `layout/` or belong to a `module`.

Since we're only working with a single page HTML/CSS wirefame, we don't have any traditional "page" types styles yet, but as we go on, we'll need to setup styles that are unique for certain pages, ie. the home page. We would do that with the following:
- `_home.scss`

### Connecting them all together

Since we broke everything out in to separate files, our `style.scss` (and subsequently our `style.css`) is completely blank. This is where Sass's import comes in:

**styles/style.scss**
```scss
// Base
@import "base/reset";
@import "base/reset";

// Layout
@import "layout/header";
@import "layout/footer";
@import "layout/grid";
// ...

// Modules
@import "modules/hero";
@import "modules/search-bar";
@import "modules/site-info";

// Pages
// ...
```

You'll notice that we didn't have to include the `_` or the `.scss` extension; this is because Sass is smart enough to know just by looking at the file.

By giving the files a underscore (`_`) at the beginning of their name, Sass knew to only import the stylesheet in to another. However since we didn't give our `style.scss` an `_`, Sass also knew to go ahead and read the file, import everything and then compile it in to a final `style.css` file.

Now we're ready to grow our CSS with our site! However, this is simply one recommendation for structuring based on research and personal experience, however there are other techniques you may read about online which I encourage you to try.

## General guidelines for CSS architecture:
- Use an underscore (`_`) if you plan to `@import` the file in to another stylesheet
- If a file starts to get longer than 200 lines, consider splitting it in to smaller chunks.
  - **Ex 1:** if you notice your `_header.scss` is growing, you can break out the styles in to a `_navigation.scss` file
  - **Ex 2:** if you find that your utilities is growing, you can split them up in to separate `_variables.scss`, `_mixins.scss`,
`_functions.scss`, etc.
- If you can't figure out where a style should go, ie. _"Does it belong in a layout, module or page style"_, just ask yourself if you ever plan to reuse that style anywhere else on the site:
  - used multiple times + a big section == `layout/`
  - used multiple times + smaller section == `module/`
  - only used for one page, no matter the size == `pages/`
- If you are including files from other sources, ie. `bootstrap.scss`, you can add a `vendor/` directory to organize code from vendor sources.

## Resources
- [How to structure a Sass project](http://thesassway.com/beginner/how-to-structure-a-sass-project)
- [Sitepoint: Architecture for a Sass Project](http://www.sitepoint.com/architecture-sass-project/)
