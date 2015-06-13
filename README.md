---
tags: setup, environment, bash
languages: ruby, bash
---

## Ruby Environment Setup Summary

If you've gone through setup on the Learn OS X application, your machine has already been setup for web development with Ruby. If you have not used the Learn OS X application, but would like to, it can be found here:

[Learn OS X application](https://learn.co/tools)

### Requirements

These are the basic requirements for Learn and Ruby. Below we describe how we set them up using the Learn app, but if you want to set up your environment yourself, you should have the basic requirements listed below:

1. XCode & GCC
2. Git
3. Ruby (probably through RVM and Rbenv or a ruby manager)
4. SQlite3
5. The rails gem (`gem install rails`)
6. The learn gem (`gem install learn-co`)

### XCode

XCode, the Apple Development Environment, should have already been installed on your machine by you (it's very difficult to automate that). You can verify this by looking in your `Applications` directory and finding the program file.

![XCode](https://dl.dropboxusercontent.com/s/ibfvkkg7s14i4fw/2015-05-03%20at%208.21%20PM.png)

### GCC

Along with XCode, we installed the XCode Command Line Tools and compiler known as GCC. You can verify this by going into your terminal and typing `gcc`.

```bash
$ gcc
clang: error: no input files
```

_Note: The `$` connotates a command meant to be typed into your prompt. You do not copy the `$` into your terminal. Your prompt is actually `// ♥`_

![GCC](https://dl.dropboxusercontent.com/s/9m0nbrhd5szrjbk/2015-05-03%20at%208.22%20PM.png)

Any output about `no input files` is fine, what you don't want to see is something like this:

```bash
$ gcc
-bash: gcc: command not found
```

You also might get something about accepting terms of service from Apple, if you do, go through that process.

### File Directory

The changes here are simple. The Learn app adds a "Development" folder to the root of your home directory. This gives you a place to organize your code.

Here are a few tips for setting up your directories:

* When creating directories, except for directories in `~` (the home directory), always use lowercase directory names for ease of access.
* When creating directory names it is preferable to use a "-" instead of a "_" to denote spaces.
* Keep all code in one place so you can access it easily.
* Make sure you have another directory to keep your resources and other things that are related to code, but aren't code. Here you might keep your local copy of [The markdown cheetsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) or other documentation.
* Remember to build your folder structure so you can easily navigate in and out of your project directories. 

### .bash_profile

Your .bash_profile is a script that runs every time you open or login to your shell. It can configure environment variables, like your `PS1` (which stores your command prompt), or `EDITOR` (which is the command other programs will use when they need to launch your default editor).

You can also create aliases for common commands so that they are shorter to use.

And finally, you can also build functions to simplify common workflows.

The Environmentalizer installs the [Flatiron Bash Profile](https://github.com/flatiron-school/dotfiles/blob/master/bash_profile) for you!

Within that bash profile are comments that explain each part. **Make sure to read them!** You can always comment sections in/out to see what they do and how they effect your prompt, shell, and environment.

Just remember, to activate a change in the dotfile, you must **reload your shell**. You can do that via opening a new tab or typing `source .bash_profile` (from the `~` directory).

You know if your `bash_profile` was setup correctly if your prompt has the Flatiron Love.

```bash
[20:23:45] ~
// ♥ 
```

### Homebrew

[Homebrew](http://brew.sh/) is a package manager for OSX. Not only will it help you install packages via commands like `brew install wget` but it will also organize the packages you install and add the appropriate locations to your path. As if that weren't enough, Homebrew also ensures that your system configurations are up to date. Commands like `brew doctor` will help you gauge the health of your system and often provide suggestions for how to fix problems.

You should be able to type in: `brew doctor` and get output from homebrew. Warning and errors are fine, as long as you don't see:

```bash
$ brew doctor
-bash: brew: command not found
```

### Git

[Git](http://en.wikipedia.org/wiki/Git_%28software%29) is the most widely used Version Control system in the world. Read about it, YOU WILL USE IT A LOT! In conjunction with GitHub, it will be used as a Version Control system for all of your projects as well as many other things you will learn. Type in: `git --version`

```bash
$ git --version
git version 2.3.5
```

Any version of git is fine, again, you just don't want to see:

```bash
$ git --version
-bash: git: command not found
```

### Sqlite3

[Sqlite3](http://en.wikipedia.org/wiki/SQLite) is a relational database system. It uses standard SQL Query language and is a great place to start experimenting with databases. Although we will use other databases later on, Sqlite3 is a great place to start. Test your sqlite with:

```bash
$ sqlite3 --version
3.8.5 2014-08-15 22:37:57 c8ade949d4a2eb3bba4702a4a0e17b405e9b6ace
```

Any version of sqlite is fine, again, you just don't want to see:

```bash
$ sqlite3 --version
-bash: sqlite3: command not found
```

#### RVM

[RVM](https://rvm.io/) is short for Ruby Version Manager. After it is installed, it manages and keeps track of the various versions of Ruby installed on your machine. You're able to view the different Ruby versions in your Terminal with commands like 'rvm list' and 'rvm use 2.2.1'. You can also do a lot more so feel free to explore. Try `rvm list`. You should see:

```bash
$ rvm list

rvm rubies

=* ruby-2.2.2 [ x86_64 ]

# => - current
# =* - current && default
#  * - default
```

As long as you don't see:

```bash
$ rvm list
-bash: rvm: command not found.
```

You're good.

#### The Learn Gem

We've installed a gem called `learn-co` for interacting with `learn.co` from your command line. Try it out by typing `learn`, as long as you don't get a bash error about `learn: command not found.` you're all set.

#### Sublime Text

[Sublime Text](http://www.sublimetext.com/) is the text editor we use at The Flatiron School. The Environmentalizer installs Sublime Text with a package manager so you can install cool themes and useful add-ons. Make sure you take the time to set it up to your liking, because you will be spending a lot of time with it! You'll see Sublime Text in your `Applications` directory.

![Sublime Text](https://dl.dropboxusercontent.com/s/wenp87iskz1gz9j/2015-05-03%20at%208.36%20PM.png)

#### Sensible Defaults

Like the `.bash_profile` these are scripts and configuration files that work in different areas. You should read through them all to see the specifics of what they are doing. Each has a specific purpose and works for different things. 

* `.gitconfig` will contain the settings that you will take advantage of when employing git in your command line. 
* `.gitignore` is a collection of files that you want git to ignore. Some files that you don't want git to track including, but not limited to, `.DS_Store` and `.env`.
* `.gemrc` Another settings file, this time for your your interaction with ruby gems.
* `.irbrc` IRB stands for "Interactive Ruby Shell". By typing the command `irb` in your command line you can open up a ruby shell and write ruby code directly in your terminal. The `.irbc` file will contain any custom settings for your use of IRB.

Remember to look through all of these files to see exactly what settings each contains and learn what effect they have on your computer. 

### Symlinks

Symlink stands for "Symbolic Link". A symlink is represented as a text string that is automatically interpreted by the operating system as a path to another file or directory. In other words a symlink is like a shortcut to another location. One will allow you to type something like `desktop` in bash to `cd` from any file directory to the desktop. It can also be used as a command, for example you will often find yourself typing `subl .` to open up the current file directory in Sublime Text. This is because the text `desktop` is symbolically linked to the desktop path ("~/Desktop") and `subl` is symbolically linked to the location on your computer where Sublime Text is stored. Some symlinks will be installed by Homebrew and others will be installed by the Environmentalizer. However, to really make your computer your own, look into creating your own!

### SSH Key

SSH stands for "Secure Shell". It is a command interface for communicating with secure servers. SSH keys serve as a means to identify yourself to an SSH server. To set up proper SSH Key Authentication you need a public key (like the one you got from GitHub) and a private key (which will be generated when the Environmentalizer runs). The private key on your computer will allow you to access the Github server with the public key without having to enter a password. You can test this with:

```bash
$ ssh git@github.com
```
You may be asked if you are sure you want to continue connecting. Enter yes. You will then see, 

```
Hi aviflombaum! You've successfully authenticated, but GitHub does not provide shell access.
```

If you get anything else, there was a problem setting up your SSH keys.

### Google Chrome

Google Chrome is a Web Browser, we suggest you use it when developing in rails.
