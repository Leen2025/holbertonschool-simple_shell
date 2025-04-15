
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
# Compilation
## Your shell will be compiled this way:

`gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh`


## files
##  Core Program Files

| File            | Description |
|-----------------|-------------|
| `main.c`        | Entry point of the program. Starts an infinite loop and calls the shell prompt. |
| `shell_loop.c`  | Main execution loop of the shell: reads, parses, and executes user commands. |
| `getLine.c`     | Implementation of input reading using `getline`. |
| `parser.c`      | Parses user input to separate commands and arguments. |
| `tokenizer.c`   | Splits input into tokens for further processing. |
| `execute.c`     | Executes user commands using `fork` and `execve`. |
| `cmd.c`         | Finds correct command paths (may be included in `parser.c` or `shell_loop.c`). |
| `special_character` | Handles cases like `exit`, `env`, and path behavior (likely split across `builtin.c`, `exits.c`, etc.). |

##  Utilities and Helpers

| File            | Description |
|-----------------|-------------|
| `_atoi.c`       | Includes `_atoi`, `_isalpha`, and helpers for delimiters or interactive checks. |
| `string.c`      | Implements string functions: `_strlen`, `_strcpy`, `_strcmp`, `_strcat`. |
| `string1.c`     | Additional string manipulation functions. |
| `memory.c`      | Functions for dynamic memory: `memcpy`, `realloc`, `free`, etc. |
| `realloc.c`     | Custom reallocation logic. |
| `lists.c`       | Linked list implementation (e.g., command history, environment). |
| `lists1.c`      | Additional list-related functions. |

##  Shell Features and Built-ins

| File            | Description |
|-----------------|-------------|
| `builtin.c`     | Built-in commands like `exit`, `env`, etc. |
| `builtin1.c`    | Additional built-in functions. |
| `getenv.c`      | Custom implementation of `getenv`. |
| `environ.c`     | Manages environment variables. |
| `getinfo.c`     | Handles `info_t` struct for runtime info. |
| `vars.c`        | Manages shell variables and replacement (`$`, `?`, etc.). |
| `exits.c`       | Logic for exiting the shell properly. |
| `history.c`     | Loads and saves command history from `.simple_shell_history`. |

##  Error Handling

| File            | Description |
|-----------------|-------------|
| `errors.c`      | Handles formatted error messages. |
| `errors1.c`     | Additional error handling utilities. |
| `err_num`       | Tracks error number/state for status codes. |


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
