# Mac Setup

First, make sure you've followed all the steps in the [setup.md](setup.md) document. 

These are additional **optional** setup instructions for those of you using Mac laptops for an enhanced experience.

First open a terminal, you can launch the finder with <kbd>Cmd</kbd>+<kbd>Space</kbd> and then type "terminal" as shown below.
	![](https://www.evernote.com/shard/s150/sh/a9abc8c3-5fcc-4d0d-bd96-24f7bf9a02bd/2dd0573f557de9ca/res/d001dece-e130-4e65-ac6e-9026cf836256/skitch.png?resizeSmall&width=832)

### Install Command Line Tools

Open a terminal and paste these lines in to install homebrew package manager and then the `wget` and `tree` commands:

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew install wget
brew install tree
```

### Add a nice terminal prompt

open a terminal and paste the following

```
touch ~/.bash_profile
open ~/.bash_profile
```

that should create and open up a file called `.bash_profile`. In that file, paste the following:

```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```

then close and reopen your terminal. `.bash_profile` is a file that is loaded every time you start your terminal. This code simply creates this nice prompt that will help you navigate when you're in the terminal

![](https://www.evernote.com/shard/s150/sh/56b16a9b-d7b5-413b-b97a-79bbc6334fda/c8d70020d85260f2/res/54b03cc8-3a0d-4aa5-a9b8-1990c71886da/skitch.png?resizeSmall&width=832)
