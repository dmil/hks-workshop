# Git and Github

## What is Git?

Keeping track of file versions is hard.
![](http://petapixel.com/assets/uploads/2015/07/psdrevisioning.jpg)

#### So what is Git, and why does it help us?
Above all else, Git is a fast and **distributed** version control system, that allows you to efficiently handle projects large and small.

Here are some problems we face as developers, and how git solves them:

#### Reverting to past versions

Git allows us to make save points at any time. These save points are called 'commits'. Once a save point is made, it's permanent, and allows us to go back to that save point at any time. From there, we can see what the code looked like at that point, or even start building off that version.

#### Keeping track of what each version 'meant'

Every commit has a description (commit message), which allows us to describe what changes were made between the current and previous commit. This is usually a description of what features were added or what bugs were fixed.

Additionally, git supports tagging, which allows us to mark a specific commit as a specific version of our code (e.g. '2.4.5').

#### Comparing changes to past versions

It's often important to see content of the actual changes that were made. This can be useful when:

* tracking down when and how a bug was introduced
* understanding the changes a team member made so you can stay up-to-date with progress
* reviewing code as a team for correctness or quality/style

Git allows us to easily see these changes (called a `diff`) for any given commit.

#### Fearlessness in making changes

In developing software, we often want to experiment in adding a feature or
refactoring (rewriting) existing code. Because git makes it easy to go back to a
known good state, we can experiment without worrying that we'll be unable to
undo the experimental work.

Section borrowed from [AlJohri](https://github.com/AlJohri/DAT-DC-12/blob/master/notebooks/intro-git.ipynb)

## What is GitHub

**GitHub** is a service that hosts **git** repositories, and provides a web app to interact / collaborate on them. GitHub isn't the only such service (for example there is also BitBucket, AWS Code Commit, or internally hosted GitLab), however it is likely the most popular. It is also host to an incredible ecosystem of open source software and community.

#### Tour of Github.com
* Your Github Page
* Collaboration (forks and branches)
* Social Features
* Pull Requests

#### Example Active Github Repo
https://github.com/18F/web-design-standards

#### GitHub, for things other than code
* Auditing system for changes on a file
* For collaboratively editing a text document
* [For drafting government web design standards!](https://github.com/18F/web-design-standards)
* [Drafting](https://github.com/twitter/innovators-patent-agreement) and [collaborating on](https://github.com/twitter/innovators-patent-agreement/issues) legal documents
* Whitehouse [comment period](https://github.com/WhiteHouse/source-code-policy/issues?q=is%3Aissue+is%3Aclosed) on policy 

#### Key Terms
* **github** - a service that hosts git remote repositories, and provides a web app to interact / collaborate on them
* **repository** - A repository is the most basic element of GitHub. They're easiest to imagine as a project's folder. A repository contains all of the project files (including documentation), and stores each file's revision history. Repositories can have multiple collaborators and can be either public or private.
* **commit** - A commit, or "revision", is an individual change to a file (or set of files). It's like when you save a file, except with Git, every time you save it creates a unique ID (a.k.a. the "SHA" or "hash") that allows you to keep record of what changes were made when and by who. Commits usually contain a commit message which is a brief description of what changes were made.
* **clone**  - A clone is a copy of a repository that lives on your computer instead of on a website's server somewhere, or the act of making that copy. With your clone you can edit the files in your preferred editor and use Git to keep track of your changes without having to be online. It is, however, connected to the remote version so that changes can be synced between the two. You can push your local changes to the remote to keep them synced when you're online.
* **fork** - A fork is a personal copy of another user's repository that lives on your account. Forks allow you to freely make changes to a project without affecting the original. Forks remain attached to the original, allowing you to submit a pull request to the original's author to update with your changes. You can also keep your fork up to date by pulling in updates from the original.
* **push** - sending changes to a remote repository and merging them into the specified branch

#### Additional Terms
* **branch** - A branch is a parallel version of a repository. It is contained within the repository, but does not affect the primary or master branch allowing you to work freely without disrupting the "live" version. When you've made the changes you want to make, you can merge your branch back into the master branch to publish your changes.
* **merge**  - Merging takes the changes from one branch (in the same repository or from a fork), and applies them into another.
* **remote repository** - A repository which is used to track the same project but resides somewhere else. To communicate with remotes, see fetch or push.
* **upstream** - the name for a remote read-only repository
* **origin** - the name for a remote read-and-write repository
* **pull request** - Pull requests are proposed changes to a repository submitted by a user and accepted or rejected by a repository's collaborators. Like issues, pull requests each have their own discussion forum. For more information, see "About pull requests."
* **merge conflict** - when two commits conflict, and thus can't be merged automatically
* **fetch**  - downloading the set of changes (commits) from a remote repository
* **pull**   - fetching changes and merging them into the current branch

Attribution 

* GitHub Glossary:  https://help.github.com/articles/github-glossary/
* Git Glossary (more technical): https://git-scm.com/docs/gitglossary
* Al's Examples: https://github.com/AlJohri/DAT-DC-12/blob/master/notebooks/intro-git.ipynb

#### Examples of open source collaboration

* https://github.com/tj/git-extras/pull/356

**Backbone forms example**

Github Issue

* https://github.com/powmedia/backbone-forms/issues/537

Pull Request (From a Fork)

* https://github.com/powmedia/backbone-forms/pull/538

## Additional resources

**Basic Git Commands**

* ​http://www.teaching-materials.org/git/slides.html
* http://rogerdudler.github.io/git-guide/

**Interactive Tutorial**

* https://try.github.io

**A Git Workflow**

* https://guides.github.com/introduction/flow/

**Understanding Git Conceptually**

* ​https://www.sbf5.com/~cduan/technical/git/
* https://cs61.seas.harvard.edu/wiki/2012/Git
* http://www.eecs.harvard.edu/~cs161/resources/git.html

**Reference Guides to Git Commands**

* https://git-scm.com/docs

**Git Screwup Guide**

* http://ohshitgit.com/

**Git/Github Cheat Sheets**

* https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf
* http://ndpsoftware.com/git-cheatsheet.html

**Git for Knowledge Workers**

* https://git-scm.com/video/what-is-version-control
* https://git-scm.com/video/quick-wins

**Licensing Open Source Code**

* http://choosealicense.com/
* https://help.github.com/articles/open-source-licensing/

**Github and Open Source Government**

* https://government.github.com/
* https://government.github.com/community/

## Set up SSH Keys

Follow these instructions. Remember, if you're using "Bash on Ubuntu on Windows" then use the "linux" instructions.
[https://help.github.com/articles/generating-an-ssh-key/](https://help.github.com/articles/generating-an-ssh-key/)


