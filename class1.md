# Introduction to the Unix Shell
# Class 1: Introduction to shell commands

## Objectives

Welcome to Introduction to the Unix Shell from fredhutch.io! 
This course introduces you to basic tasks using the Unix shell,
including:
- working with files and directories
- combining commands using pipes
- repeating commands using for loops and shell scripts 
- searching files and their contents
- customizing your shell

A solid understanding of these basic principles is required prior to tackling material in our intermediate high performance computing (HPC) courses for both the on-premise clusters and cloud computing.

By the end of this lesson,
you should be able to:
- FIXME
- viewing files and directories
- navigating paths 

## Getting started

Check software installation

GUIs vs CLIs

command prompt

bash vs zsh

First command: username?
```
whoami
```

Next command: where am I in my computer?
```
pwd
```

What things are in this place in my computer?
```
ls
```

Change working directory to Desktop:

```
cd Desktop/
```

Download project directory
- view files online [here](https://github.com/fredhutchio/unix_shell_intro/tree/master/example_unix_project)
- click [here](https://github.com/fredhutchio/unix_shell_intro/raw/master/example_unix_project.zip) to download zipped file

Download project:

On Linux:
```
wget https://raw.githubusercontent.com/fredhutchio/unix_shell_intro/master/example_unix_project.zip
```

On Mac:
```
curl https://raw.githubusercontent.com/fredhutchio/unix_shell_intro/master/example_unix_project.zip -o example_unix_project.zip
```

Unzip project:
```
unzip example_unix_project.zip
```

Describe project
- why a project?
- file and directory organization

## Navigating files and directories

relative vs absolute paths

. and ..

flags
```
ls -F
```

> Do spaces matter?

```
ls -a
```

## Working with files and directories

mkdir doc

cd doc

nano notes.md

mv

cp

rm

rmdir

## Combining commands

wildcards

manuals, help

wc

redirection

cat

sort

pipes

head

options with values

> what to do if I get stuck?


## Wrapping up

make sure work is saved

review how to get back into work

review objectives

preview next class's objectives

## Errata

https://merely-useful.github.io/py-rse/bash-basics.html
