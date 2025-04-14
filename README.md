
![Holberton school logo](https://secure.meetupstatic.com/photos/event/b/c/5/6/highres_475548214.jpeg)
# simple_shell project repository

This repository contains the files for Holberton's **simple_shell**. It can be compiled using GCC and will execute a simple shell that can be used for some basic tasks and programs most commonly found in the /bin/ folder.

# Pre-requisites
# Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

# General
Who designed and implemented the original Unix operating system
Who wrote the first version of the UNIX shell
Who invented the B programming language (the direct predecessor to the C programming language)
Who is Ken Thompson
How does a shell work
What is a pid and a ppid
How to manipulate the environment of the current process
What is the difference between a function and a system call
How to create processes
What are the three prototypes of main
How does the shell use the PATH to find the programs
How to execute another program with the execve system call
How to suspend the execution of a process until one of its children terminates
What is EOF / “end-of-file”?
# Requirements
#  General
Allowed editors: vi, vim, emacs
All your files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
All your files should end with a new line
A README.md file, at the root of the folder of the project is mandatory
Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
Your shell should not have any memory leaks
No more than 5 functions per file
All your header files should be include guarded
Use system calls only when you need to (why?)
# GitHub
*There should be one project repository per group. If you and your partner have a repository with the same name in both your accounts, you risk a 0% score. Add your partner as a collaborator. *

More Info
Output
Unless specified otherwise, your program must have the exact same output as sh (/bin/sh) as well as the exact same error output.
The only difference is when you print an error, the name of the program must be equivalent to your argv[0] (See below)
Example of error with sh:

$ echo "qwerty" | /bin/sh
/bin/sh: 1: qwerty: not found
$ echo "qwerty" | /bin/../bin/sh
/bin/../bin/sh: 1: qwerty: not found
$
Same error with your program hsh:

$ echo "qwerty" | ./hsh
./hsh: 1: qwerty: not found
$ echo "qwerty" | ./././hsh
./././hsh: 1: qwerty: not found
$

# List of allowed functions and system calls
access (man 2 access)
chdir (man 2 chdir)
close (man 2 close)
closedir (man 3 closedir)
execve (man 2 execve)
exit (man 3 exit)
_exit (man 2 _exit)
fflush (man 3 fflush)
fork (man 2 fork)
free (man 3 free)
getcwd (man 3 getcwd)
getline (man 3 getline)
getpid (man 2 getpid)
isatty (man 3 isatty)
kill (man 2 kill)
malloc (man 3 malloc)
open (man 2 open)
opendir (man 3 opendir)
perror (man 3 perror)
read (man 2 read)
readdir (man 3 readdir)
signal (man 2 signal)
stat (__xstat) (man 2 stat)
lstat (__lxstat) (man 2 lstat)
fstat (__fxstat) (man 2 fstat)
strtok (man 3 strtok)
wait (man 2 wait)
waitpid (man 2 waitpid)
wait3 (man 2 wait3)
wait4 (man 2 wait4)
write (man 2 write)

# Compilation
## Your shell will be compiled this way:

`gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh`


# files
- README.md - description about the project repo
- man_1_simple_shell - is the man page for the shell we are going to write.
- AUTHORS - file at the  root of your repository, listing all individuals having contributed content to the repository. 
- main.h - is the header file which contains the standared header file and prototype of o function used in the program.
- main.c - initialize the program with infinite loop by call the prompt function
- prompt.c - it use getline system call to read the input from the user and run infinite loop with fork to keep prompt going.
- special_character - It identiies if the special inputs such as if the frist input is slash,the user typed exit or env...
- string.c -it handles the strings(string length, write string,find string in directory,concatane strings....)
- cmd.c - it finds the command the user entered.
- execute.c - execute the command.

## How to add Author file
`Bash script for generating the list of authors in git repo`
```
#!/bin/sh

git shortlog -se \
  | perl -spe 's/^\s+\d+\s+//' \
  | sed -e '/^CommitSyncScript.*$/d' \
  > AUTHORS
  ```
### Authorized functions and macros:
- access (man 2 access)
- chdir (man 2 chdir)
- close (man 2 close)
- closedir (man 3 closedir)
- execve (man 2 execve)
- exit (man 3 exit)
- _exit (man 2 _exit)
- fflush (man 3 fflush)
- fork (man 2 fork)
- free (man 3 free)
- getcwd (man 3 getcwd)
- getline (man 3 getline)
- isatty (man 3 isatty)
- kill (man 2 kill)
- malloc (man 3 malloc)
- open (man 2 open)
- opendir (man 3 opendir)
- perror (man 3 perror)
- read (man 2 read)
- readdir (man 3 readdir)
- signal (man 2 signal)
- stat (__xstat) (man 2 stat)
- lstat (__lxstat) (man 2 lstat)
- fstat (__fxstat) (man 2 fstat)
- strtok (man 3 strtok)
- wait (man 2 wait)
- waitpid (man 2 waitpid)
- wait3 (man 2 wait3)
- wait4 (man 2 wait4)
- write (man 2 write)

### GCC command to compile:
`
gcc -Wall -Werror -Wextra -pedantic *.c -o hsh
`

This wil compile all the '.c' files and change the output's name to 'hsh'.

### Template to test output:
=============
$ ./hsh

($) 

hsh main.c shell.c

$ exit
$


After you clone this repository and compile the program with the command above, you will generate a file called **hsh** that can be executed by entering  ```./hsh``` in your shell.

The output after the program is executed should look something like this:
```
$|
```
Where you will get a prompt in the shape of a dollar sign so you can start typing commands into your shell.  Agood example of how it should execute is the command shown above were the user enters 'ls' and then gets a list of the directory contents.
## Function Prototypes:

Brief description of functions contained in project:

**_strcmpdir** :  compares strings to find dir.
**find_command** :  finds command to execute in path routes.
**charput** :  writes the character like putchar.
**place** :  similar to puts in C.
**_strlen** :  string length.
**str_concat** :  concatenate strings.
**lookforslash** :  identify if first char is a '/'.
**compareExit** :  checks if user typed exit.
**compareEnv** :  checks if user typed env.
**execute_proc** :  receives command and args from getline to be executed.
**identify_string** :  returns pointer with folder address.
**prompt** :  infinite loop with fork to keep prompt going.
**controlC**: avoid program closing when pressing ctrl + c.
**main**: initialize program.

README.md: this.

## General Flow Chart:

<a href="https://ibb.co/1MMmc0J"><img src="https://i.ibb.co/5kkRZ1x/Untitled-Diagram.png" alt="Untitled-Diagram" border="0"></a>

### Contact Info:

Git: [Leen Alsaleh ](https://github.com/Leen2025), [Dana Alshehri](https://github.com/d-alshehri) 
