# Week 1: Intro to Course & Front-end Tools

In this course, we'll be focusing on intermediate-to-advanced front-end web development techniques and best practices. We'll be introducing the following tools and concepts:

### Tools
- _**Git & GitHub**_ for version control & collaboration
- _**Prepros**_ for CSS compiling and build processing
- _**Chrome DevTools**_ for advanced CSS/JavaScript debugging
- _**Atom**_ for text editing with built-in Git integration

### Concepts
- **Responsive web design** (cross-device)
- **CSS authoring** (preprocessors)
- **CSS architecture/frameworks** (DRY/SMACSS)
- **HTML prototyping** (usability testing)
- **JavaScript** (interactive programming)

The goal for this course is for each student to have a basic grasp of the tooling, yet a thorough understanding of the concepts as presented and their necessity in the web design & development process.

You'll also notice a few over-arching themes being repeated throughout the course that, while not core to curriculum, will provide a better understanding of how the development process works at large.

#### Themes
- **Marketing vs product design** (website vs web-app)
- **Craftsmanship** (hacking)
- **Agile development**
- **Open-source software**
- **Contribution/Attribution** (on the web)

Let's get started by introducing the foundational concept that will help us track and share our code, **version control**.

## Version Control

**Version control** (also known as **source control management**) is a system that records changes to a file or set of files over time so that you can recall specific versions later. Many popular systems include aspects of version control built-in to the software like word processors (ie. Google Docs, etc) and content management systems (ie. WordPress, etc).

- [Wikipedia: Revision Control](https://en.wikipedia.org/wiki/Revision_control)
- [Git SCM: Getting started - about version control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)


There's multiple types of version control systems available, including [CVS](http://www.nongnu.org/cvs/), [SVN](http://subversion.apache.org/), [Git](https://git-scm.com/) et al. Each system is catered to a specific type of workflow for collaboration, but generally all provide the same file versioning/history capabilities.

- [Wikipedia: List of types of version control](https://en.wikipedia.org/wiki/List_of_revision_control_software)

**Video: [Git Basics: What is Version Control?](https://vimeo.com/41027679)**
[![What is Version Control](images/git/what-is-version-control.png)](https://vimeo.com/41027679)

### What is Git/GitHub?
[![Git SCM Logo](images/git/git-logo.png)](https://git-scm.com/)

**[Git](https://git-scm.com/) is the fastest growing and most popular version control system used to track and share documents today.**

Git provides common version control capabilities, but with it's own, unique organizational workflow. Git's [branching model concept](#branch) encourages a *feature-based workflow*, allowing people to seamlessly switch back and forth between different features they're working on and experiment without impacting the integrity of their code-base.

Git also allows groups of people to work on the same documents (often code) at the same time, and without stepping on each other's toes. It's a distributed, version control system.

[![Github](images/git/github-logo.png)](https://github.com/)

**[GitHub](https://github.com/) is a web-based, Git repository hosting service. _(ie. a 'hub' for Git repo's, get it?)_**

Unlike Git, which is strictly a command-line (CLI) tool, GitHub provides a web-based graphical interface and desktop client for managing Git repositories.

GitHub also provides access control and several collaboration features such as bug tracking, feature requests, task management, and wikis for every project.

### Git concepts
- [Git: The advantages of Git compared to other source control systems](https://git-scm.com/about/)
- [Git: Getting started - Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

### GitHub setup

1. Sign up for a [free GitHub account](https://github.com/join)
  - Setup [Two Factor Authentication (2FA)](https://github.com/blog/1614-two-factor-authentication) as an additional security measure
2. Complete [ART258 GitHub account form](http://goo.gl/forms/QubL6AJy0F)
3. *Download [GitHub Desktop app](https://desktop.github.com/)
  - [GitHub for Mac](https://central.github.com/mac/latest)
  - [GitHub for PC](https://github-windows.s3.amazonaws.com/GitHubSetup.exe)

**The GitHub Desktop app should already be installed on the KOA 103 studio classroom computers.*

#### Repository
A Git repository is nothing more than a directory (ie. folder) on a computer. Any file in your 'repo' will be tracked and a history of the changes will be recorded (unless [explicitly ignored](http://git-scm.com/docs/gitignore), which we'll talk about a bit later).

#### Branch
A Git branch is a working copy of your code, *in a specific state*. When you're working on a project, you're going to have a bunch of different features or ideas in progress at any given time – some of which are ready to go, and others which are not. Branching exists to help you manage this workflow.

#### Commit
A commit saves your current changes to your current branch. Once you start making changes in a repository, Git will start tracking those changes. Whenever you add, edit, or delete a file, you're making a commit, and adding them to your branch. This process of adding commits keeps track of your progress as you work on a feature branch.

#### Push/Pull (Sync)
A good practice in web development is to create backups of your projects. This is where _**GitHub**_ comes in, as a central repository hosting service for Git projects. Once you've wrapped up with your coding session, it's a good idea to sync your local repository with GitHub so all of your code changes are archived. If you're working on a team or between multiple machines, it's also a good idea to sync your local repository before you start working as well.

#### Pull Request
In the *[GitHub development workflow](#github-development-workflow)*, theres a `master` branch that keeps the final record of the code ready for deployment. To get code from our feature branches in to our master branch, we need to make a pull request.

#### Merge
In Git, merging brings the changes in two branches together. A pull request is a request to merge a set of commits from one branch in to another. Merges can be performed on your local machine to combine changes from two feature branches before syncing, and making a pull request to the `master` branch on Github.

### GitHub development workflow

As we go through the semester, we'll cover different aspects of Git & GitHub within our workflow. At a [high-level](https://en.wikipedia.org/wiki/High-_and_low-level), we'll be following the [GitHub-Flow]() methodology for development with some slight adjustments for this course.

- Anything in the `master` branch is deployable
- To work on something new, create a descriptively named branch off of `master` (ie: `home-page-bug-fix`)
- Commit to that branch locally and regularly push (ie. sync) your work to the same named branch on GitHub
- When you need feedback or help, create an issue and mention myself and/or another student using the @username syntax (ie, @micjamking)
- When you are ready to submit your code assignment, create a pull request:
  - Have 2 other students review your work by mentioning them using the @username syntax in your pull request description (not the title!)
  - If your classmates find any issues, make the fixes locally and push the changes to the same remote branch
  - Once your code has been reviewed by 2 classmates and your code is ready to turn in, create a new comment on your pull request with the words `@micjamking: Final Submission`; this will send me a notification that your assignment is ready to be graded.

## Prepros
[![Prepros Logo](images/prepros/prepros-logo.png)](https://prepros.io/)

One of the bigger concepts of the semester will be authoring CSS using [Sass](http://sass-lang.com/). Sass (Syntactically Awesome Stylesheets) is a scripting language that preprocesses (ie. compiles in to) CSS. Sass extends CSS, providing features that are not yet available like variables, nesting of rules, mixins/functions, and operators to simplify our styling process and make our code more modular, scalable, and maintainable.

- [Wikipedia: Sass](https://en.wikipedia.org/wiki/Sass_(stylesheet_language))

Since browsers only read CSS in its original syntax, we need to use a program to compile our written Sass in to CSS so be served up to the browser. Similar to Git and other front-end tools, Sass was built as a command-line utility. In this course, we'll be using **[Prepros](https://prepros.io/)**, a third-party graphical user-interface (GUI) for CSS preprocessing, to assist us.

Along with Sass compiling, Prepros will also help out in other aspects of our web development build cycle, including:

- CSS prefixing
- Browser refresh & behavior synchronization
- File concatenation & minification
- Image optimization
- FTP client

We'll be diving in to this tool starting Week 2 and will cover each of the features above in detail in the subsequent weeks.

## Chrome DevTools
[![Chrome Devtools Logo](images/devtools/chrome-devtools-logo.png)](https://developers.google.com/web/tools/chrome-devtools/)

When developing a website or application using web technologies, it's necessary to be able to debug the site for issues while viewing it in the browser or on a device. [Google Chrome's Developer Tools](https://developers.google.com/web/tools/chrome-devtools/) (ie. Chrome DevTools) are a set of built-in authoring and debugging tools for web technologies (HTML/CSS/JavaScript).

Chrome Developer Tools (DevTools) helps you develop, test, and debug your web sites and applications directly from the Google Chrome browser. DevTools provides web developers the following capabilities which are essential to create usable, well functioning websites:

- Inspection of the Document Object Model (DOM) and styles of the currently running page.
- Debug JavaScript with breakpoints and the console.
- Interact with a page and record performance using the Timeline & Auditing tools.
- Test your pages on mobile using device emulation mode.

Chrome DevTools can also serve as a complete authoring environment, similar to traditional text editors like [Atom](#atom) or Sublime Text, however setup is an advanced topic and only certain aspects will be covered in this course.

If you're completely unfamiliar with the concept of debugging or have used other debuggers like Firebug but are inexperienced with Chrome DevTools, I highly recommend checking out the free online training course on [Chrome DevTools by Code School](https://www.codeschool.com/courses/discover-devtools). It's taught by [Paul Irish](http://www.paulirish.com/), one of the Chrome Developer team members, but uses [Code Schools](https://www.codeschool.com/) highly interactive, educational platform, so I find it more approachable than the Chrome DevTool documentation as an introduction to the tool.

We'll be covering different aspects and topics on Chrome DevTools throughout the semester as we go through the web development process.

## Atom
[![Atom Logo](images/atom/atom-logo.png)](https://atom.io/)

**[Atom](https://atom.io/) is a "hackable text editor for the 21st century".** Similar to *[Adobe Dreamweaver](http://www.adobe.com/products/dreamweaver.html)*, *[Brackets](http://brackets.io/)*, *[Sublime Text](http://www.sublimetext.com/)*, and *[Textmate](https://macromates.com/) (for OSX)*, Atom is a standalone text editor built for coding/programming. However, unlike the above editors, Atom comes with [built-in Git integration](https://atom.io/docs/v1.0.7/using-atom-version-control-in-atom), is [completely customizable](https://atom.io/docs/v1.0.7/hacking-atom-tools-of-the-trade) through JavaScript & CSS, and best of all, is [open-source](http://blog.atom.io/2014/05/06/atom-is-now-open-source.html) (ie. free).

**Video: [GitHub presents: Atom 1.0](https://youtu.be/Y7aEiVwBAdk)**
[![Atom](images/atom/atom.png)](https://youtu.be/Y7aEiVwBAdk)

As a web developer, a text editor is your primary tool for crafting sites and apps, so finding an editor that you're comfortable with and is configurable to match your workflow is important.

Below are a few features which are important to have in a text editor.
- Autocompletion
- File browser/file search
- Extensibility/plugins for additional functionality
- Theming

Along with the above features, Atom also includes [integration with Git](https://atom.io/docs/v1.0.7/using-atom-version-control-in-atom), providing the following additional capabilities:
- Quickly rewind to a previous commit (`cmd-alt-z`)
- Display the list of all the untracked (ie. new) and modified files in the project (`cmd-shift-b`)
- Edit commit messages (if using Git CLI)
- Highlight the status of our untracked and modified files within the tree-view, gutter and status bar of the Atom interface.  

Students may use any text editor they prefer for this course, however Atom will assist in learning the Git concepts and can be configured to fit any particular workflow. It is recommended to atleast try the editor for the initial few weeks, since it will be used for presenting the exercises and should be easier to follow along with.

## HTML/CSS Review

### Creating a basic HTML page

**Topics Covered**
- Basic HTML structure
- CSS linking
- ID's versus Classes
- Practical naming
- Positioning
  - Relative
  - Absolute
  - Fixed
- Floats
  - Clearing floats
- Pseudo-elements
  - `:before`/`:after`
- Pseudo-classes
  - `:first-child`/`:last-child`
  - `:nth-child()`


#### Declare your !DOCTYPE
This tells the browser what version of HTML you are using and must come before the HTML tag. The HTML5 doctype is the simplest to remember:

```html
<!DOCTYPE html>
```

#### Create your opening and closing HTML tags.
This is where all your HTML will go.

```html
<!DOCTYPE html>
<html>
  ...
</html>
```

Create your opening and closing `<head>` and `<body>` tags.
The `<head>` tag must include a title for the document. The head is also where you will include your stylesheets, scripts and meta tags. In your `<head>` tag, you will need to declare what type of character set you will be using for the document.

```html
<meta charset="UTF-8">
```

The `<body>` tag will define the document’s body and where your HTML will be.

```html
<head>
  <meta charset="UTF-8">
  <title>My First In Class Assignment</title>
</head>
<body>
  ...
</body>
```
All together now.
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My First In Class Assignment</title>
</head>
<body>
  ...
</body>
</html>
```

Save your file in an appropriate place as `index.html`. This will be the home page for the site we're creating.

#### Break your down page structure

Study your page structure and understand how things can be broken down into sections. By keeping everything simple, we can grasp the general layout and work on the details later.

Our website has 5 main sections:

- header
- search
- hero section
- information
- footer

Let’s think about every section as a separate element and divide them accordingly within our HTML. It's also helpful to create comments to keep track of each element.

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My First In Class Assignment</title>
</head>
<body>

  <!-- Header Section -->
  <header>
  </header>

  <!-- Search Section -->
  <section>
  </section>

  <!-- Hero Section -->
  <section>
  </section>

  <!-- Information Section -->
  <section>
  </section>

  <!-- Footer Section -->
  <footer>
  </footer>

</body>
</html>
```

#### IDs vs Classes (ie. serial number vs barcodes)

`id`: unique identifiers _(serial number)_
- Only one ID per element
- Only only ID of that kind per page
- Browser will navigate (scroll to) element with ID in url (ie. http://yourdomain.com#comments)

`class`: reusable classifiers _(barcodes)_
- Same class on multiple elements allowed
- Multiple classes on same elements allowed

**When should you use an ID versus a Class?**

**Rule of thumb:** us id's for behavior and classes for styling

An element can have both an `id` and a `class`, so start with a `class`. If you need something to be unique for a specific behavior (like navigation), add a unique `id` for that page.

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My First In Class Assignment</title>
</head>
<body>

  <!-- Header Section -->
  <header class="main-header">
  </header>

  <!-- Search Section -->
  <section class="search">
  </section>

  <!-- Hero Section -->
  <section class="hero">
  </section>

  <!-- Info Section -->
  <section class="site-info">
  </section>

  <!-- Footer Section -->
  <footer class="main-footer">
  </footer>

</body>
</html>
```

#### Let’s start to style

Create your stylesheet and save it in a folder called `styles`. The folder should live in the same directory as your home page `index.html`. However you name it is up to you, but let’s keep it simple and call it `style.css`.

You should now have a folder named `styles` with a file called `style.css` within it.

#### Linking your stylesheet

In your `index.html`, link your stylesheet in the `<head>` of your document as such:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>My First In Class Assignment</title>
  <link rel="stylesheet" href="styles/style.css">
</head>
...
```
**Question:**
*If we moved `styles.css` out of the `styles` folder and in to the parent directory with `index.html` what would the new link be?*

#### Testing
In your `style.css`, give the body a background color of your choice.

```css
body {
  background-color: #FFCC00;
}
```

Open your `index.html` file in your browser and confirm the background color was applied to the web page.

#### Styling sections
Let’s add more styling to the page. Since there is no content yet, none of the elements we created are being shown. We need to add a height to each element:

```css
.main-header {
  height: 60px;
  background: green;
}

.search {
  height: 60px;
  background: orange;
}

.hero {
  height: 460px;
  background: red;
}

.site-info {
  height: 260px;
  background: purple;
}

.main-footer {
  height: 200px;
  background: blue;
}

```
**Question:**
What would be the best way (most effecicient/fastest) way if I wanted to apply the same styling to multiple elements?

#### Reset browser default styling
All browsers will apply a default styling to elements thats slightly different from each other so we need to 'reset' the styles so we can start from a consistent place cross-browser.

A very simple reset can be something like this:
```css
* {
  margin: 0;
  padding: 0;
}
```
However, this can be over simplistic and incomplete. There are additional CSS resets avaialble which also supply a handy set of defaults for things like typography and form controls. Let take a look at [Eric Meyer's CSS Reset](http://meyerweb.com/eric/tools/css/reset/).
A copy is included in this repo here: [reset.css](styles/reset.css)


This new file should be declared before our `style.css` file so we start with a clean document, free of any default browser styling.

```html
<head>
  <meta charset="UTF-8">
  <title>My First In Class Assignment</title>
  <link rel="stylesheet" href="styles/reset.css">
  <link rel="stylesheet" href="styles/style.css">
</head>
```

There are also other CSS resets available, including:
- [normalize.css](https://github.com/necolas/normalize.css/)
- [HTML5 Doctor reset](http://html5doctor.com/html-5-reset-stylesheet/)
- [Yahoo's YUI3 reset](https://github.com/yui/yui3/blob/master/src/cssreset/css/cssreset.css)

#### Content Area and Centering

Let’s add content areas in each section and give it a width, add a background color, and center it. Make the width 960px.

**index.html**
```html
<!-- Header Section -->
<header class="main-header">
	<div class=content>
	</div>
</header>

<!-- Search Section -->
<section class="search">
	<div class=content>
	</div>
</section>

<!-- Hero Section -->
<section class="hero">
	<div class=content>
	</div>
</section>

<!-- Info Section -->
<section class="site-info">
  <div class=content>
	</div>
</section>

<!-- Footer Section -->
<footer class="main-footer">
	<div class=content>
	</div>
</footer>
```

**style.css**
```css
.content {
  width: 960px;
  margin: 0 auto;
  background: white;
}
```
**Question:**
Why can’t we see the background color we added? What do we need to do?

```css
.content {
  width: 960px;
  height: inherit;
  margin: 0 auto;
  background: white;
}
```

#### Adding a logo and navigation
Within our header, add one `<div>` element and one `<nav>` element. One will be your logo and one will be your main navigation. Give them a class.

```html
<header class="main-header">
  <div class="content">
  	<div class="logo">
  	</div>

  	<nav class="main-nav">
  	</nav>
	</div>
</header>
```

Once these items have been added, give each one a width, height and background color in your css.

```css
.logo {
  height: 60px;
  width: 100px;
  background: gray;
}

.main-nav {
  height: 60px;
  width: 400px;
  background: purple;
}
```
Add content or text within each element.

#### Absolute positioning elements
We need to practice different positioning. Under the normal circumstances, you will probably not want to position items absolute unless you need them to be in a very specific location.

In your css, add `position: absolute;` to your `.logo` and `.main-nav`. If you position something absolute, it will remove the element out of normal flow (how a browser normally renders something) and will reposition it on the page and will not affect any element around it.

Now, add `top: 0;` and `left: 0;` to your `.logo`.

```css
.logo {
  width: 100px;
  height: 40px;
  background: gray;
  position: absolute;
  top: 0;
  left: 0;
}
```

**What happens?**

Now try to position the main navigation absolute with a `top: 0;` and `right: 0;`.

**What happens?**

Absolute position looks for the first parent element which has `position: relative;` applied to it and will reposition it’s coordinates based on that parent element.

**Question:**
How do we bring the two elements (logo and main nav) back into the container?

#### Create columns
Let’s skip the search bar row and move on to the next HTML section. Create three `<div>` within the proper wrapper.
```html
<section class="hero">
  <div class="content">
  	<div class="hero-01 columns">
  	</div>
    <div class="hero-02 columns">
  	</div>
    <div class="hero-03 columns">
  	</div>
  </div>
</section>
```
How wide should each column be? Add a `width: 50%;` to `.hero-01` and `width:25%;` to `.hero-02` and `.hero-03`, a `height: 100px` to each one, and a unique background color to each element.

#### Floating
To make all items display inline to each other in a row, we need to float them. In layman's terms, floating takes an element out of normal flow and moves them either to the far left or far right (depending on how you float the element).

**Try this:**
- Float all elements left
- Float all elements right. Wha
- Change the widths to all three elements to 60% and keep the float right. What happens?
- Change everything back to the original widths (50% and 25%) and make `.hero-01` `float: left` and `.hero-02` and `.hero-03` `float: right`.

Resources:
- [CSS Trick: All About Floats](http://css-tricks.com/all-about-floats/)

#### Clearing
Any time you float an element, it takes it out of normal flow and will position it according to how you specify it. To reset the flow of content, you need to clear your floats.
In the past, a common technique would be to add an empty element at after all of the floats and in your css put `clear:both;` to remove all floats. That  createa unnecessary markup and isn't scalable.

On your main section `.hero`, add the element `height: auto;`. Let’s say we don’t know how tall the content area will be. What happens?
Because the content is removed from normal flow, the main div thinks there is nothing in it, so it collapses the height to 0.

How do we display the two sections that just disappeared? We need to clear our floats.

Most frameworks or other coders add a special rule to their CSS. We will add a rule in the beginning of our CSS document as follows:
```css
.content:after {
  content: "";
  display: table;
  clear: both;
}
```
This selector `.content:after` may look unfamiliar, but it reads as follow
> _All pseudo `:after` elements belonging to a `.content` element._

The `:after` is known as a CSS _pseudo-class_. This type of pseudo class is only available in IE8+ and other modern browsers.

Now, if you have floats in anything with the class of `.content`, it will automatically clear it and you don’t have to worry about setting a height.

_Note: Clearing only works on floats, not elements positioned absolutely._

#### More Pseudos
Let’s clean up our HTML and how everything looks. Each column should have some spacing, so let’s change the width from 75% to 74% and 25% to 24%.

Let’s give each column a left margin of 2% by adding it to our `.column` class.
```css
.hero-01 {
  background: brown;
  float: left;
  height: 460px;
  width: 74%;
}

.hero-02 {
  background: pink;
  float: right;
  height: 230px;
  width: 24%;
}

.hero-03 {
  background: blue;
  float: right;
  height: 230px;
  width: 24%;
}

.column {
  margin: 0 0 0 2%;
}
```

Now, we have margin on both elements, but we don’t need a margin on the first element. How do we get rid of it? Let’s use `:first-child`, a _pseudo-class_.

`element:first-child` applies style rules to the first element of the matched elements.

```css
.column:first-child {
  margin: 0;
}
```

_Note: :last-child will not work in early versions of IE8 or lower, so avoid using it._

`:nth-child()`

What about making odd columns a different color?
```css
element:nth-child(odd) {
  background: red;
}
```
What about making only the second column a different color?
```css
element:nth-child(2) {
  background: red;
}
```
What about making every sixth column a different color?
```css
element:nth-child(6n) {
  background: red;
}
```

**References:**
- [Mozilla: Writing Efficient CSS](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Writing_efficient_CSS)
- [CSS Specificity](http://www.standardista.com/wp-content/uploads/2012/01/specificity3.pdf)
