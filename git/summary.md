Summary of Git Lessons
======================

![](git-header.jpg)

## Table of Content

 - [Introduction](#Introduction)
 - [Important Terms](#Important-Terminologies)
 - [Commands](#Commands)

## Intoduction
 Git is a source code manager (SCM) which is another name of version control system (VCM). It is a decentralized where each user has the entire repository on their computer.

## Important Terminologies
  - __Working Directory__ is the files that you see in your computer's file system
  - __Staging Area__ a file in the Git directory that stores information about what will go into your next commit
  - __Repository (Repo)__ is a directory which contains your project work, as well as a few files which are used to communicate with Git

## Commands
  - ```git init```
    creates a new, empty repository in the current directory. However, there is a hidden __.git__ directory insides which holds all of the configuration files.
  - ```git clone <path-to-repository> ```
    command is used to create an identical copy of an existing repository.
      - ``<renamed-title>`` is the second argument which tells git to __*rename*__ the project to given title but is __*optional*__
  - ```git status```
    displays the current status of the repository
  - ```git log```
    displays (__SHA__, __author__, __date__, __message__) all of the commits of a repository.
      - ```↓``` and ```↑``` are used to scroll down and up the lines and ```spacebar``` and ```b``` are used to scroll down and up pages respectively. ```q``` is used to quit.
      - ```--oneline``` flag is used to list one commit per line.
      - ```--stat``` is used to list detailed info (__files__, __no.of.lines__, __summary__) per commit.
      -  ```--patch``` or ```-p``` is used to list __actual changes__, __location of lines__ and __modified files__ per commit.
      - ```-w``` is used to ignore whitespaces from the changes per commit
  - ```git show <SHA>```
    displays the commit by the given __SHA__. First seven digits of SHA are enough to identify commit. All of the flags mentioned with ```git log``` command can be used with it.
  - ```git add <file1> <file2> ... <fileN>```
    move files from the Working Directory to the Staging Index.
    Alternatively, the period ```.``` can be used in place of a list of files to tell Git to add the current directory.
  - ```git commit```
    takes files from the Staging Index and saves them in the repository. It opens the code editor that is specified in your configuration to take the commit message.
      - ```-m``` flag __bypass the Editor__(if configured) by taking the commit message in same line. e.g ```git commit __-m__ *"commit message"*```
  - ```git diff```
    show changes that have been made but haven't been committed







