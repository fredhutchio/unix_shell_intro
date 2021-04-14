## Unix Shell Crash Course

This tutorial covers basic Unix (aka shell, command line) 
concepts required as pre-requisites for other fredhutch.io courses,
like [RNAseq analysis](https://fredhutchio.github.io/rnaseq/skills/).
It is not intended to be a replacement for the complete [Introduction to Unix](https://fredhutchio.github.io/unix_shell_intro) course.
This material is also a convenient cheatsheet for participants enrolled in more advanced courses.

Before proceeding with these training materials,
please ensure you have access to a Unix shell on your computer.
- **Mac OSX**:  You can access the command line through an application called Terminal.
You can either search for this in Finder, 
or use the Go drop-down menu to locate it in the Utilities folder.
- **Windows**: We recommend one of two options.
  - **Git for Windows**: This lightweight software is a shell emulator designed for working with Git version control, but also that allows Windows users to interact with general Unix commands.
  It is a good choice if you are interested primarily in computing remotely (which is the case for intermediate fredhutch.io courses).
  Go [here](https://gitforwindows.org) for installation instructions,
  noting that the application you'll be using to access the Unix shell is called Git Bash.
  - **WSL**: Windows 10 comes with a new feature called Windows Subsystem for Linux (WSL) that allows you to access Unix tools.
  This is a fairly extensive installation that can be tricky,
  but may be useful if you are interested in working with Unix frequently on your own computer.
  Instructions can be found [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

By the end of this crash course,
you should be able to:
- connect to the Fred Hutch on-premise compute resource (`rhino`)
- navigate local and remote directory structures using paths
- work with files and directories using the Unix command line and in-shell text editor (`nano`)
- automate tasks with Unix commands using pipes and shell scripts

## Getting set up

Open the software you'll be using to access the Unix shell (Mac: Terminal, Windows: WSL or Git Bash).

We can run our first Unix command by typing the following into the shell window:

```bash
whoami
```

[logging on to rhino](https://sciwiki.fredhutch.org/compdemos/first_rhino/)

Download project:

On Linux:
```
wget https://raw.githubusercontent.com/fredhutchio/unix_shell_intro/master/example_unix_project.zip
```

Unzip project, inspecting contents of folder before and after:
```
ls
unzip example_unix_project.zip
ls
```

## Navigating directories

where am I in my computer?
```
pwd
```

What things are in this place in my computer?
```
ls
```

Change working directory to project:

```
cd Desktop/
```

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

shared network drives (accessing fast)

> popout explaining other ways to access home and fast

## Working with files and directories

working with files (head, mv, cp, rm, etc)

in-shell text editor (nano)

## Automating tasks

- shell scripts (creating and running)
- pipes

## Wrapping up
