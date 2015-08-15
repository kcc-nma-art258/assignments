# Week 1: Introduction to Course & Front-end Tooling

In this course, we'll be focusing on intermediate–advanced front-end web development techniques and best practices. We'll be introducing the following tools and concepts, following industry standards with a focus on the user-centered design process:

### Tools
- _**Git & GitHub**_ for version control & collaboration
- _**Atom**_ for hacking/text editing with built-in Git integration
- _**Prepros**_ for CSS compiling and build processing
- _**Chrome DevTools**_ for advanced CSS/JavaScript debugging

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

### Types of Version Control

There's multiple types of version control systems available, including [CVS](http://www.nongnu.org/cvs/), [SVN](http://subversion.apache.org/), [Git](https://git-scm.com/) et al. Each system is catered to a specific type of workflow for collaboration, but generally provide the same file versioning capabilities.

- [Wikipedia: List of types of version control](https://en.wikipedia.org/wiki/List_of_revision_control_software)
- [The top 7 open source version control system](http://www.smashingmagazine.com/2008/09/the-top-7-open-source-version-control-systems/)
- [Git: Getting started - about version control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

**Video: [Git Basics: What is Version Control?](https://vimeo.com/41027679)**
[![What is Version Control](images/git/what-is-version-control.png)](https://vimeo.com/41027679)

### What is Git/GitHub?

**[Git](https://git-scm.com/) is the most popular version control system that developers use to track and share code.**

Git provides a history of revisions or changes to files and an organization system around it.

Git allows groups of people to work on the same documents (often code) at the same time, and without stepping on each other's toes. It's a distributed, version control system.

**[GitHub](https://github.com/) is a web-based, Git project (ie. repository) hosting service.**

Unlike Git, which is strictly a command-line (CLI) tool, GitHub provides a web-based graphical interface and desktop client for managing Git repositories.

GitHub also provides access control and several collaboration features such as bug tracking, feature requests, task management, and wikis for every project.

### Git concepts
[Git: Getting started - Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

#### Repository
A Git repository is nothing more than a project. Any file in your repo will be tracked and a history of the changes will be recorded (unless [explicitly ignored](http://git-scm.com/docs/gitignore), which we'll talk about a bit later).

#### Branch
A Git branch is a working copy of your code, *in specific state*. When you're working on a project, you're going to have a bunch of different features or ideas in progress at any given time – some of which are ready to go, and others which are not. Branching exists to help you manage this workflow.

#### Commit
A commit saves your current changes to your current branch. Once you start making changes in a repository, Git will start tracking those changes. Whenever you add, edit, or delete a file, you're making a commit, and adding them to your branch. This process of adding commits keeps track of your progress as you work on a feature branch.

#### Push/Pull (Sync)
A good practice in web development is to create backups of your projects. This is where _**GitHub**_ comes in, as a central repository hosting service for Git projects. Once you've wrapped up with your coding session, it's a good idea to sync your local repository with GitHub so all of your code changes are archived.

#### Pull Request
In the *[GitHub development workflow](#github-development-workflow)*, theres a `master` branch that keeps the final record of the code ready for deployment. To get code from our feature branches in to our master branch, we need to make a pull request.

#### Merge
In Git, merging brings the changes in two branches together. A pull request is a merge that requires permission. Merges can be performed on your local machine to combine changes from two feature branches before syncing, and making a pull request to the `master` branch on Github.

### GitHub setup

1. Sign up for a [free GitHub account](https://github.com/join)
2. Complete [ART258 GitHub account form](http://goo.gl/forms/QubL6AJy0F)
3. *Download [GitHub Desktop app](https://desktop.github.com/)
  - [GitHub for Mac](https://central.github.com/mac/latest)
  - [GitHub for PC](https://github-windows.s3.amazonaws.com/GitHubSetup.exe)

**GitHub Desktop app should already be installed on the studio classroom computers.*
### GitHub development workflow

- Anything in the `master` branch is deployable
- To work on something new, create a descriptively named branch off of `master` (ie: `home-page-bug-fix`)
- Commit to that branch locally and regularly push (ie. sync) your work to the same named branch on GitHub
- When you need feedback or help, create an issue and mention myself and/or another student using the @username syntax (ie, @micjamking)
- When you are ready to submit your code assignment, open a pull request on the GitHub website
  - Have 2 other students review the work by mentioning them using the @username syntax in your pull request description (not the title!)
  - If your classmates find any issues, make the fixes locally and push the changes to the same remote branch
  - Once your code has been reviewed by 2 classmates and your code is ready to turn in, create a new comment on your pull request with the words `@micjamking: Final Submission`; this will send me a notification that your assignment is ready to be graded.

## Atom

## Prepros

## Chrome DevTools

## HTML/CSS Review
