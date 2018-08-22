# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

* show current working directory path
* creating a directory: mkdir + directory name
* deleting a directory: rm -r #deletes all the child directories too
* creating a file using `touch` command: touch + file name
* deleting a file: rm + name of file
* renaming a file: mv + old file + new file name
* listing hidden files: ls -a
* copying a file from one directory to another: cp + directory/file + name of new file
* moving up a directory: cd ..
* listing all contents of directory in long format: ls -l
* copying all files into a directory: cp * directory 

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

* `ls` # lists the files and directories in current directory
* `ls -a`  # lists all contents of directory including hidden files and directories
* `ls -l`  # lists all contents of directory in long format
* `ls -lh` # lists the contents of a directory in long format with file size in human readable format (e.g. 1K 234M 2G)
* `ls -lah` # lists the contents of a directory, including hidden files, in long format with file size in human readable format (e.g. 1K 234M 2G)
* `ls -t`  # lists the files in order of time they were last modified (newest first) instead of alphabetical order
* `ls -Glp` # lists the contents of a directory in long format without group name, and displays directories with /  

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

* `ls -S` # sorts by file size
* `ls -d` # lists directories only
* `ls -u` # lists files by file access time
* `ls -m` # lists the names as a comma separated list
* `ls -R` # lists subdirectories as well

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > xargs executes the argument, building an execution pipeline from standard input. 

For example:
```
$ echo 'one two three' | xargs mkdir 
ls
one two three
```
 

