Summary of Git Lessons
======================

![](git-header.jpg)

## Table of Content

 - [Introduction](#Introduction)
 - [Important Terms](#Important-Terminologies)
 - [Commands](#Commands)
 - [Git Ignore Understanding](#Git-Ignore)
 - [Commit Referencing](#Commit-References)
 - [Remotes](#Remotes)
 - [Additional Resources](#Resources)

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
      - ```--stat``` shows the files that have been changed and how many lines were added or removed in them
      - ```--author=<author-name>``` filters the commit by the __author-name__ e.g ```git log --author="paul lewis"```
      - ```--grep=<key-phrase>``` filters the commit by the given __key-phrase__. e.g ```git log --grep="css bug"```
  - ```git show <SHA>```
    displays the commit by the given __SHA__. First seven digits of SHA are enough to identify commit. All of the flags mentioned with ```git log``` command can be used with it.
  - ```git add <file1> <file2> ... <fileN>```
    move files from the Working Directory to the Staging Index.
    Alternatively, the period ```.``` can be used in place of a list of files to tell Git to add the current directory.
  - ```git commit```
    takes files from the Staging Index and saves them in the repository. It opens the code editor that is specified in your configuration to take the commit message.
      - ```-m``` flag __bypass the Editor__(if configured) by taking the commit message in same line. e.g ```git commit -m "commit message"```
      - ```--amend``` alter the most-recent commit. Running it on a clean Working Directory will let you provide a new commit message. However, If you want to add some changes in your last commit, just stage the changes and run ```git commit --amend```
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
  - ```git revert <SHA>```
    reverts a commit by the given __<SHA>__
  - ```git reset <reference-to-commit>```
    move the HEAD and current branch pointer to the __<referenced commit>__
    - ```--hard``` erases the commits
    - ```--soft``` moves the committed changes to staging index
    - ```--mixed``` moves the changes to the working directory. It is optional which means if no flag is provided ```--mixed``` is used by-default
    - It is good to make a __backup branch__ by ```git branch backup```. So that you can fast-forward merge it to the tip
  - ```git remote```
    list the available remotes on a repo in short form.
    - ```-v``` list the detail about connection to the avilable remotes.
    - ```add <remote-name> <url>``` adds remote of <remote-name> to the current repo
  - ```git push <remote-shortname> <branch>``` push the changes from given branch __<branch>__ to the remote repository __<remote-shorname>__
  - ```git pull <remote-shortname> <branch>``` get the changes of given branch __<branch>__ from the remote repository __<remote-shorname>__ and merge to local
  - ```git fetch <remote-shortname> <branch>``` get the changes of given branch __<branch>__ from the remote repository __<remote-shorname>__ but do not merge the changes to the local-repo
  - ```git shortlog```
    displays an alphabetical list of names and the commit messages that go along with them
    - ```-n``` shows the number of commits (rather than each commit's message)
    - ```-s``` sorts the commits numerically (rather than alphabetically by author name).


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

## Commit-References
  Here are special characters called "Ancestry References" that we can use to tell Git about these relative references. Those characters are:
  - ```^``` indicates the parent commit
  - ```~``` indicates the first parent commit
  Here's how we can refer to previous commits:

  ### The Parent Commit
  The following indicate the parent commit of the current commit
  - ```HEAD^```
  - ```HEAD~```
  - ```HEAD~1```

  ### The Grandparent Commit
  The following indicate the grandparent commit of the current commit
  - ```HEAD^^```
  - ``HEAD~2``

  ### The Great-Grandparent Commit
  The following indicate the great-grandparent commit of the current commit
  - ```HEAD^^^```
  - ```HEAD~3```

  The main difference between the ```^``` and the ```~``` is when a commit is created from a merge. A merge commit has two parents. With a merge commit, the ```^``` reference is used to indicate the first parent of the commit while ```^2``` indicates the second parent. The first parent is the branch you were on when you ran git merge while the second parent is the branch that was merged in

## Resources
  - [Dotfiles](https://dotfiles.github.io/)
  - [Learn Git from app](https://github.com/jlord/git-it-electron)