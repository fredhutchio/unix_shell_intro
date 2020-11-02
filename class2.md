# Introduction to the Unix Shell
# Class 2: Repeating commands

## Objectives

- finding things
- subshells (vs back ticks)
- loops
- shell scripts
- history

## Finding things

**Objectives:** grep to select lines in text which match patterns, find to find files whose names match patterns, nesting files, text vs binary files

* move to doc subdirectory
* `cat manuscript.txt`
* `grep hypothesis manuscript.txt` : find lines that contain hypothesis
* `grep is manuscript.txt` : find lines that contain “day”
* `grep -w is manuscript.txt` : searches only for whole words
* `grep -n is manuscript.txt` : includes the numbers on lines that match
* `grep -n -w is manuscript.txt` : combine flags
* `grep -n -w -i method manuscript.txt` : make case insensitive
* `grep -n -w -v method manuscript.txt` : invert selection, only lines that do NOT contain method
* the real strength of grep, and the origin of its name, is “regular expressions,” which describes ways of programmatically describing text strings/search patterns, but we don't have time to cover these today (many awesome lessons and tutorials online)
* difference between grep and find
* `find . -type d` : look for things that are directories in given path
* `find . -type f` : look for files instead
* find is automatically recursive (keeps drilling down into file hierarchy)
  * can specify depth: `find . -maxdepth 1 -type f`  
  * or `-mindepth`
* can match by name: `find . -name *.csv` (will only give one filename! expands name prior to running command)
* correct way: `find . -name '*.csv'`
* find similar to list, but has more refined parameter searching
* can combine together: count all lines in a group of files
  * `wc -l $(find . -name '*.txt')`
  * nesting or subshell
* equivalent command: `wc -l ./data/BLCA.csv ./data/BRCA.csv ...`
* can also combine find and grep: 
  * `grep stage $(find .. -name '*.txt')`
* today we've only talked about text files, what about images, databases, etc? those are binary (machine readable)

## Loops

**Objectives:** write loops that apply commands to series of files, trace values in loops, explain variables vs values, why spaces and punctuation shouldn't be used in file names, history, executing commands again

* what if you wanted to perform the same commands over and over again on multiple files?
* good example is move: `mv *.dat original-*.dat` but doesn't work
* you can perform these operations using a loop
* example looking at first three lines in each file
```
for filename in BLCA.csv BRCA.csv
  do
    head -3 $filename
  done
```
  * what does this look like when you arrow back up?
  * explain syntax: filename is variable, what does it stand for? how is it represented later?
  * shell prompt changes, if you get stuck, use control+C to get out
  * can specify whatever variable name you want
  * why might it be problematic to have filenames with spaces?
* you can include multiple commands in a loop:
```
for filename in *.dat
do
echo $filename
head -100 $filename | tail -20
done
```
  * use of wildcard. what does echo do? why is this useful for loops?

## Shell scripts

**Objectives:** write shell script to run command or series of commands for fixed set of files, run shell script from command line, write shell script to operate on set of files defined on command line, create pipelines including user-written shell scripts

* go back to molecules in nelle's directory
* create file called `middle.sh` and add this command: `head -15 octane.pdb | tail -5`
* `bash middle.sh`
  * `.sh` means it's a shell script
  * very important to make these in a text editor, rather than in word!
* edit `middle.sh` and replace file name with `"$1"`
  * quotations accommodates spaces in filenames
* `bash middle.sh octane.pdb`, should get same output
  * try another file: `bash middle.sh pentane.pdb`
* edit `middle.sh` with `head “$2” “$1” | tail “$3”`
* `bash middle.sh pentane.pdb -20 -5`
* to remember what you've done, and allow for other people to use: add comments to top of file
```
#select lines from middle of a file
#usage: middle.sh filename -end_line -num_lines
```
  * explain comments
* what if we wanted to operate on many files? create new file: `sorted.sh`
* `wc -l “$@” | sort -n`
* `bash sorted.sh *.pdb ../creatures/*.dat`
* add comment!
* save last few lines of history to file to remember how to do work again later:
  * `history | tail -4 > redo-figure.sh`
  * `history | tail -5 | colrm 1 7` (1-7 characters)


## Wrapping up

make sure work is saved

review how to get back into work

review objectives

preview next class's objectives
