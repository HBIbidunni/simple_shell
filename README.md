## ALX C - Simple Shell Team Project
The Collaboration on this ALX C- Simple Shell project was done by team of two people and we were required to create a simple shell that mimics the bash shell. Our simple shell shall be called `hsh`.

## Resources
* Unix shell
* Thompson shell

## The Project was completed utilizing
* Betty linter
* C programming language
* Shell

## General Requirement for the Simple Shell Project
* All the files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
* All the files should end with a new line
* A README.md file, at the root of the folder of the project is mandatory
* The Betty style of coding is used. It will be checked using betty-style.pl and betty-doc.pl
* Shell should not have any memory leaks
* No more than 5 functions per file
* All the header files in the project should be include guarded
* Write a README with the description of your project
* You should have an [AUTHORS](./AUTHORS) file at the root of your repository, listing all individuals having contributed content to the repository.  

## Synopsis
* In this project the `hsh` is simple implementation of a UNIX command line interpreter.

## Description
*  Our simple shell `hsh` can interpret and execute command line arguments read from the standard input. In a terminal line or file, it reads the arguments line by line and then interprets and executes these command lines as if the lines are a valid command.

## How hsh works and its usage
* The simple shell `hsh` works by printing a prompt and waiting for a command line from the user. 
* It then creates a child process in which the command is checked. Similarly,checks for built-ins, aliases in the PATH, and local executable programs are created. 
* Afterwards, the child process is replaced by the command line, which accepts arguments. 
* After the command is completed, the program returns to the parent process and prints the prompt, signaling that the program is ready to receive a new command. 

* All the files are to be compiled on Ubuntu 20.04 LTS machine using: 

   `gcc -Wall -Werror -Wextra -pedantic * .c -o hsh`. 

* Once compiled, to start the program in interactive shell mode, run: `$./hsh`. 
* To exit the program, run: hsh $ exit or Ctrl-D or enter "exit" (with or without a status).
* The `hsh` shell supports most shell commands, such as `cat`, `pwd`, `home`, and more.

## Invocation
Usage: `hsh`[filename]

To invoke `hsh`, compile all .c files in the repository and run the resulting executable. `hsh` can be invoked both interactively and non-interactively. If `hsh` is invoked with standard inputnot connected to a terminal, it reads and executes received commands in order.

For instance:

`$ echo "echo 'hello'" | ./hsh`

`'hello'`

`$`

If `hsh` is invoked with standard input connected to a terminal, an interactive shell is opened. When executing interactively,`hsh` displays the prompt `$`  when it is ready to read a command.

For instance:

`$./hsh`

`$`

Alternatively, if command line arguments are supplied upon invocation, `hsh` treats the first argument as a file from which to read commands. The supplied file should contain one command per line. `hsh` runs each of the commands contained in the file in order before exiting.

For instance:

`$ cat test` 

`echo 'hello'`

`$ ./hsh test`

`'hello'`

`$`

## Environment
Upon invocation, `hsh` receives and copies the environment of the parent process in which it was executed. This environment is an array of name-value strings describing variables in the format `NAME=VALUE`. A few key environmental variables are:

HOME

PWD

OLDPWD

PATH

## Command Execution
After receiving a command, `hsh` tokenizes it into words using `" "` as a delimiter. The first word is considered the command and all remaining words are considered arguments to that command.
`hsh` then proceeds with the following actions:

* If the first character of the command is neither a slash (`\`) nor dot (`.`), the shell searches for it in the list of shell builtins. If there exists a builtin by that name, the builtin is invoked.
* If the first character of the command is none of a slash (`\`), dot (`.`), nor builtin, hsh searches each element of the PATH environmental variable for a directory containing an executable file by that name.
* If the first character of the command is a slash (`\`) or dot (`.`) or either of the above searches was successful, the shell executes the named program with any remaining given arguments in a separate execution environment.

## Exit Status
* `hsh` returns the exit status of the last command executed, with zero indicating success and non-zero indicating failure.

* If a command is not found, the return status is `127`; if a command is found but is not executable, the return status is `126`.

* All builtins return zero on success and one or two on incorrect usage (indicated by a corresponding error message).

## Signals
While running in interactive mode, `hsh` ignores the keyboard input `Ctrl+c`. Alternatively, an input of end-of-file (`Ctrl+d`) will exit the program.

User hits `Ctrl+d` in the third line.

`$ ./hsh`

`$ ^C`

`$ ^C`

`$`

## Variable Replacement
`hsh` interprets the $ character for variable replacement.

`$ENV_VARIABLE`

`$?`


`$$`

## Comments
`hsh` ignores all words and characters preceeded by a # character on a line.

For instance:

`$ echo 'hello' #this will be ignored!`

`'hello'`

## Operators
`hsh` specially interprets the following operator characters:

; - Command separator

&& - AND logical operator

|| - OR logical operator

# Builtin Commands

-> cd

alias

exit

env

setenv

unsetenv

We discovered and understand:
* How a shell works and finds commands
* Creating, forking and working with processes
* Executing a program from another program
* Handling dynamic memory allocation in a large program
* Pair programming and team work
* Building a test suite to check our own code

## Prepared by
* HBIbidunni
----
