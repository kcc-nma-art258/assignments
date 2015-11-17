# Week 3: Continue Review of Basic Web Development Techniques

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Review of GitHub, DevTools and HTML/CSS building blocks](#review-of-github-devtools-and-htmlcss-building-blocks)
  - [Atom Settings](#atom-settings)
  - [GitHub Review](#github-review)
  - [Setting up Chrome DevTools](#setting-up-chrome-devtools)
    - [Live-editing in Chrome](#live-editing-in-chrome)
    - [Resources](#resources)
- [If you are already done or finish early...](#if-you-are-already-done-or-finish-early)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Review of GitHub, DevTools and HTML/CSS building blocks

### Atom Settings

We're going to be building up to more complex sites over the week, so lets configure our editor to ignore some
files that we don't want to get in our way while we're developing. This is a common practice and a configurable setting within most popular editors.

Copy `(cmd + C)` the list of ignored file types below:

```git
 *.cfg, .git, .hg, .svn, .DS_Store, ._*, Thumbs.db
```

Open Atom, and open *Atom > Preferences* from the menu bar.

![Atom Screenshot](images/atom-screenshot-1.png)

Click on the **Settings** menu, and paste the code in the *Ignored Names* list.

![Atom Screenshot 2](images/atom-screenshot-2.png)

Click on the **Packages** menu, and type in `tree-view` in the *Installed Packages* input field. When the **tree-view** package appears under *Core Packages*, click on the settings button.

![Atom Screenshot 3](images/atom-screenshot-3.png)

Under the Settings section, check *Hide Ignored Names*

![Atom Screenshot 4](images/atom-screenshot-4.png)

Now our configuration files won't get in the way!

### GitHub Review

To make sure we're all on the same page, let's start by grabbing a fresh copy of our `assignments` project. If you already started one and completed the assignment, you can skip this part. However, if you got stuck or still confused about GitHub, I encourage you to do the following.

First, go to github.com, find your fork of the assignments project, and got to the *Settings* in the bottom right side-bar.

![Github](images/github-1.png)

Scroll down to the bottom where it says **Danger Zone** and click the big red button that says `Delete this repository`.

![Github 2](images/github-2.png)

Click the button and retype the name of the repository (ie. `assignments`) to confirm deletion, then click the button that says `I understand the consequences, delete this repository`.

![Github 3](images/github-3.png)

This might sound scary, but everything will be fine since we still have a local copy on our computers we can send back up to the cloud at any time. For now, let's remove the project from GitHub Desktop as well...

![Github 4](images/github-4.png)

...and rename the file in finder to something else like `assignments_old`.

![Github 5](images/github-5.png)

On github.com, navigate to the [kcc-nma-art258/assigments](https://github.com/kcc-nma-art258/assignments) and fork the repository again.

![Github 6](images/github-6.png)

And then in Github Desktop, clone the project again.

![Github 7](images/github-7.png)

Once the project has finished cloning, create a new branch called `gh-pages`.

![Github 8](images/github-8.png)

Right-click, and open the project in Atom. Once the project has been opened in Atom, highlight all of the files in the folder, then right-click and select DELETE. Confirm `Move to Trash`.

![Github 9](images/github-9.png)

Back in Atom, commit those files and then sync. Now you're ready to start the Homework assignment! If you would like access to your previous projects, I can walk around and assist each of you with copying the resources back in your project from `assignments_old` individually.

### Setting up Chrome DevTools

When developing in the browser, you'll want to debug and see changes to your code while you're working. With Chrome Developer Tools, we have the ability to debug as well as edit our code live in the browser.

Let's start by opening up the Chrome Developer Tools, by clicking on the menu icon in the top right corner; then *More Tools > Developer Tools* or by using the shortcut `(cmd + opt + I)`

![Chrome DevTools Screenshot](images/chrome-devtools-1.png)

This will pop-open a pane for doing debugging and authoring.

The main panels we'll be working with for the moment are the *Elements* and *Sources* Panel.

**Elements Panel**

This is where we can see a live preview of our HTML & CSS. You can edit both here and see the changes take effect live on the page. This is also how you can see if something is going wrong.

![Chrome DevTools Screenshot 2](images/chrome-devtools-2.png)

**Sources Panel**

The sources panel acts as the editor of Chrome DevTools, allowing you to saving the changes CSS & JS files and they'll be applied live on the page without reloading. HTML files can be edited here as well, however their changes require a page refresh.

![Chrome DevTools Screenshot 3](images/chrome-devtools-3.png)

To setup live editing, add your projects workspace to the DevTools by right-clicking in the *Sources* sidebar pane and selecting `Add Folder to Workspace`.

![Chrome DevTools Screenshot 4](images/chrome-devtools-4.png)

*You can add individual projects at a time, but I simply add my entire *projects* folder to make things easier.*

Once you add the folder, Chrome will ask you to confirm access for DevTools. Just click `Allow`.

![Chrome DevTools Screenshot 5](images/chrome-devtools-5.png)

Once you click allow, you'll see the folder added to your left hand pane. You can now browse your local web projects in Chrome like any other editor!

#### Live-editing in Chrome

To see live editing in Chrome, you can select a CSS or JavaScript file from the sources sidebar pane...

![Chrome DevTools Screenshot 6](images/chrome-devtools-6.png)

or by selecting a CSS file from the Styles sub-panel in the *Elements* panel.

![Chrome DevTools Screenshot 7](images/chrome-devtools-7.png)

*Clicking on `style.css:1` will pull up the CSS file loaded from the network*

Once you have the CSS file pulled up, right-click within the *Sources* panel code view and select `Map to Network Resource`.

![Chrome DevTools Screenshot 8](images/chrome-devtools-8.png)

*If you started from the Elements panel, the option will say `Map to File System Resource` instead.*

Chrome will then pop open the file quick-finder to select the local or network file that matches the current file. Once you select the file, Chrome will ask you to restart for the changes to take affect.

![Chrome DevTools Screenshot 9](images/chrome-devtools-9.png)

By default, Chrome Devtools will load the files from the server, which is what you're accessing and manipulating in the *Elements* panel. With Workspaces enabled, we have local copies of the same files available for editing.

Below is a shot of the network files and local file resources expand; network files have a globe icon and local files have a folder icon.

![Chrome DevTools Screenshot 10](images/chrome-devtools-10.png)

When we map a network and local resources together, Chrome will reflect the local changes we're making on the live site we're viewing. You'll know everything is setup if you only see your local file afterwards, but no corresponding network resource.

![Chrome DevTools Screenshot 11](images/chrome-devtools-11.png)

Now when you make edits to your CSS & JS, they'll be reflected live in the browser without refreshing!

![Chrome DevTools Screenshot 12](images/devtools-live-edit.gif)

The changes you make are also saved to the file system just like a normal editor with the `(cmd + S)` shortcut. You can also edit and make changes to other files including HTML files, however these changes won't be reflected live.

#### Resources
- [Chrome Developer Tools: Authoring and Development Workflow](https://developer.chrome.com/devtools/docs/authoring-development-workflow)
- [Google Developers: Inspect and Tweak Your Pages](https://developers.google.com/web/tools/iterate/inspect-styles/basics)
- [Google Developers: Set up persistence with DevTools Workspaces](https://developers.google.com/web/tools/setup/workspace/setup-workflow)
- [Remy Sharp: My workflow - Never having to leave DevTools](https://remysharp.com/2012/12/21/my-workflow-never-having-to-leave-devtools)

## If you are already done or finish early...
- Help at least two of your classmates by [reviewing their code](https://help.github.com/articles/using-pull-requests/#reviewing-proposed-changes)
- [Code School: Discover DevTools (Ch. 1 & 2)](http://discover-devtools.codeschool.com/)
- [Code School: Assembling Sass (Level 1)](https://www.codeschool.com/courses/assembling-sass)
