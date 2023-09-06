# ASE 2023 - 2024 overview

## Weeks 1 - 2: Linux literacy, git
### Week 1: Working in the commmandline
* basic commands - ls, rm , mv, cp etc
* simple bash scripting
    - variables, loops and control flow 
    - functions
    - commandline arguments

### Week 2: Intro to git 
* concept of version control
* a way to have a backup of your code and all of its history 
* distinction between git (the software) and hosting platforms (github, gitlab,
  self-hosting etc...)
* initialising a directory as a git repo
* create git account and set up ssh key
* initialising .git dir and setting upstream url
* add, commit, pull, push
* fixing merge conflicts
* branching
* Rebase
* Cherrypicking


## Weeks 3 - 6: Python programming fundamentals

We will be using the git concepts we had learned the previous week in parallel
with writing a Python program to generate mazes. This will be done in order to
reinforce these concepts, and to show how git is used in practise while writing more
complicated software.

### Week 3: Installing conda and managing the programming environment
* downloading miniconda and installing it
* writing an environment.yml file with both conda and pip dependencies
* navigating between virtual environments
* getting VScode extensions for python and ipython

### Week 4: basic python programming
* introduce the "code-along" programming assignment - a simple maze generation
  algorithm that outputs an animation of the maze being made
* python variables and operators
    - assigning variables (explain the difference between by value vs by reference)
    - lists and list operations
    - dicts and their operations
* module imports - using external APIs. Here we will use pyray, a module for
  animation/drawing to output our mazes to the screen

### Week 5: OOP and TDD
* advanced python concepts
    - functions are first class objects in Python
    - recursion
    - list comprehension
    - generators and the `yield` keyword
* classes and inheritence
* TDD
    - the unittest class
    - how to write good tests
    - concept of writing tests first, having your program break, and then write code to pass the test

## Week 6: Jupyter notebooks
- install Jupyter notebook stuff
- setting things up via vscode
- showing some of the benefits of using this, like visualising plots, using
  already executed cells as "checkpoints"
- importing python modules into notebooks

## Weeks 7 - 12: Deep learning
Week 6 sets us up nicely for the next few weeks as we will almost exclusively be
using jupyter notebooks now. These lessons will be identical to the ones covered
last year, please check the [github repo](https://github.com/jayathungek/aim-lab-sessions) for details.

### Week 7
* introduction to numpy
* basic operations and theory

### Week 8
* introduction to pandas
* exercises

### Week 9
* intro to pytorch and data loading

### Week 10
* basic pytorch classification model

### Week 11
* improving the training loop of the basic model

### Week 12
* logging, saving and deploying model output
