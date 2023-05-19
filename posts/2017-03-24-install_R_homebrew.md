---
title: Installing R with Homebrew on Mac OS X
author: 'Justin Bankes'
date: '2017-03-24'
slug: homebrew_r
categories: [install]
tags: [rmarkdown, homebrew, OSX]
description: ''
---

This document explains how to install R and RStudio with Homebrew on Mac OS.

### Main Instructions
The steps below will install _Homebrew_, _R_, and _RStudio_. Open a terminal and
run the following commands.

1. Install _Homebrew_.

  ```bash
  usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```
  This command will download, install, and set up _Homebrew_. The first time a
  `brew` command runs it will ask for a password.

2. Install _R_ with the following commands:
  ```bash
  brew tap homebrew/science # adds another source for applications.
  brew install r            # runs installer of r
  ```
  The first command is necessary if you want to add science/math type
  applications. The second command handles all the installation of _R_ itself.
  As of 3.25.2017 this installs version . This can take a while because
  _Homebrew_ downloads then builds the tools though it tends to be faster an
  easier than manual installation.

3. Install _RStudio_ with the following command:
  ```bash
  brew cask install rstudio
  ```
  Try navigating to _RStudio_ to verify installation.

4. _Optional_ Set up _RStudio_ to work from the command line.
  ```bash
  echo "alias rstudio='open -a RStudio'" >> ~/.bash_profile
  source ~/.bash_profile
  ```
  This sets up your bash profile to run _RStudio_ when `rstudio` is entered into
  the command line (i.e. `rstudio example.rmd`). It adds and `alias` to your
  `~/.bash_profile` so you can remove it if you want.

  This concludes the installation of _RStudio_. The rest of this documentation
  is more on Homebrew.

### Background and Info on Homebrew.

#### What is Homebrew.
[Homebrew](https://brew.sh) is a package manager for _macOS_ (_MacOS X_) that
claims to be _The missing package manager to macOS_. You can use this to find
open source and UNIX tools that most Linux distros have but don't natively
show up on Mac (i.e. wget and imagemagick). It works from the command line and
it makes installing, updating, and removing packages easier.

#### Some useful commands:
_Be careful with these because they do alter/remove applications._

1. Update and Upgrade your packages.

    ```bash
    $ brew update   # update the formula
    $ brew upgrade  # Upgrade outdated, unpinned brews.
    ```

2. List your installed packages.

    ```bash
    $ brew list     # lists all installed brews
    ```

3. Remove an Application
    ```bash
    $ brew uninstall <formula>
    ```

For more information on _Homebrew_ navigate to [brew.sh](https://brew.sh).
