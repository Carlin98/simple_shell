# Simple Shell   

## General     
* Who designed and implemented the original Unix operating system    
* Who wrote the first version of the UNIX shell    
* Who invented the B programming language (the direct predecessor to the C programming language)    
* Who is Ken Thompson    
* How does a shell work    
* What is a pid and a ppid    
* How to manipulate the environment of the current process    
* What is the difference between a function and a system call    
* How to create processes    
* What are the three prototypes of main    
* How does the shell use the PATH to find the programs   
* How to execute another program with the execve system call   
* How to suspend the execution of a process until one of its children terminates    
* What is EOF / “end-of-file”?    

## Output   
* Unless specified otherwise, your program must have the exact same output as sh (/bin/sh) as well as the exact same error output.    
* The only difference is when you print an error, the name of the program must be equivalent to your argv[0]    

## Compilation   
Your shell will be compiled this way:   
`gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh`

## Testing    
Your shell should work like this in interactive mode:    
~~~~
$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$
~~~~

But also in non-interactive mode:
~~~~
$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$
~~~~

## Tasks    
* 0. Write a beautiful code that passes the Betty checks    
* 1. Write a UNIX command line interpreter.    
	* Usage: simple_shell    
Your Shell should:    
	* Display a prompt and wait for the user to type a command. A command line always ends with a new line.    
	* The prompt is displayed again each time a command has been executed.    
	* The command lines are simple, no semicolons, no pipes, no redirections or any other advanced features.    
	* The command lines are made only of one word. No arguments will be passed to programs.    
	* If an executable cannot be found, print an error message and display the prompt again.    
	* Handle errors.    
	* You have to handle the “end of file” condition (Ctrl+D)     

You don’t have to:    
	* use the PATH    
	* implement built-ins    
	* handle special characters : ", ', `, \, *, &, #     
	* be able to move the cursor    
	* handle commands with arguments    
*execve will be the core part of your Shell, don’t forget to pass the environ to it…*
* 2. Simple shell 0.1 +    
	* Handle command lines with arguments    
* 3. Simple shell 0.2 +    
	* Handle the PATH    
	* fork must not be called if the command doesn’t exist     
* 4. Simple shell 0.3 +    
	* Implement the exit built-in, that exits the shell     
	* Usage: exit    
	* You don’t have to handle any argument to the built-in exit     
* 5. Simple shell 0.4 +    
	* Implement the env built-in, that prints the current environment     


