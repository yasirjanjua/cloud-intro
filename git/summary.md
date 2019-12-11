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
      - ```--graph --all``` displays tree view of all branches
  - ```git show <SHA>```
    displays the commit by the given __SHA__. First seven digits of SHA are enough to identify commit. All of the flags mentioned with ```git log``` command can be used with it.
  - ```git add <file1> <file2> ... <fileN>```
    move files from the Working Directory to the Staging Index.
    Alternatively, the period ```.``` can be used in place of a list of files to tell Git to add the current directory.
  - ```git commit```
    takes files from the Staging Index and saves them in the repository. It opens the code editor that is specified in your configuration to take the commit message.
      - ```-m``` flag __bypass the Editor__(if configured) by taking the commit message in same line. e.g ```git commit -m "commit message"```
  - ```git diff```
    shows changes that have been made but haven't been committed
  - ```git tag```
    lists the available tags on current branch.
      - ```-a <tag> <SHA>``` adds a tag __<tag>__ on given commit __<SHA>__. ```<SHA>``` is optional, if not provided then tag is added to the current commit
      - ```-d <tag>``` deletes a tag by given tag __<tag>__ name
  - ```git branch```
    list all the branches available on a repo.
      - ```<branch-name>``` creates a new branch with given __branch-name__
      - ```-d <branch-name>``` deletes the branch by given __branch-name__
  - ```git checkout <branch-name>```
    switches to given __branch-name__
      - ```-b <branch-name>``` creates a new branch by the given name and switches to it in single command




## Git Ignore
  ```.gitignore``` file is used to tell Git about the files that Git should not track. This file should be placed in the same directory that the ```.git``` directory is in.
  In the ```.gitignore``` file, you can use the following:
  blank lines can be used for spacing
  - __#__ marks line as a comment
  - __*__ matches 0 or more characters
  - __?__ matches 1 character
  - __[abc]__ matches a, b, _or_ c
  - __**__ matches nested directories
    - a/**/z matches
      ```a/z```,
      ```a/b/z```,
      ``a/b/c/z``



