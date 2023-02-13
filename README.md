## ALX C - Simple Shell Team Project
The Collaboration on this ALX C- Simple Shell project was done by team of two people and we were required to create a simple shell that mimics the bash shell. Our simple shell shall be called `hsh`.

## Resources
* [Unix shell](./Unix shell)
* [Thompson shell](./Thompson shell)

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
* You should have an AUTHORS file at the root of your repository, listing all individuals having contributed content to the repository. Format see [Authors](./Authors) 

## Synopsis
* In this project the `hsh` is simple implementation of a UNIX command line interpreter.

## Description
*  Our simple shell `hsh` can interpret and execute command line arguments read from the standard input. In a terminal line or file, it reads the arguments line by line and then interprets and executes these command lines as if the lines are a valid command.

## How hsh works and its usage
* The `simple shell- hsh` works by printing a prompt and waiting for a command line from the user. It then creates a child process in which the command is checked. Similarly,checks for built-ins, aliases in the PATH, and local executable programs are created. Afterwards, the child process is replaced by the command line, which accepts arguments. After the command is completed, the program returns to the parent process and prints the prompt, signaling that the program is ready to receive a new command. 

All the files are to be compiled on Ubuntu 20.04 LTS machine using `gcc -Wall -Werror -Wextra -pedantic * .c -o hsh`. Once compiled, to start the program in interactive shell mode, run: `$./hsh`. To exit the program, run: `hsh $ exit or Ctrl-D or enter "exit" (with or without a status)`.The hsh shell supports most shell commands, such as cat, pwd, ls -la and more.

## Invocation
Usage: `hsh`[filename]
To invoke `hsh`, compile all .c files in the repository and run the resulting executable. `hsh` can be invoked both interactively and non-interactively. If `hsh` is invoked with standard inputnot connected to a terminal, it reads and executes received commands in order.

For instance:
`$ echo "echo 'hello'" | ./hsh
'hello'
$`

If `hsh` is invoked with standard input connected to a terminal, an interactive shell is opened. When executing interactively,`hsh` displays the prompt `$`  when it is ready to read a command.

For instance:
`$./hsh
$`

Alternatively, if command line arguments are supplied upon invocation, `hsh` treats the first argument as a file from which to read commands. The supplied file should contain one command per line. `hsh` runs each of the commands contained in the file in order before exiting.

For instance:
`$ cat test 
echo 'hello'
$ ./hsh test
'hello'
$`

