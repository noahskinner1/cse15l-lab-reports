# This is lab report 1 for CSE 15L

## 1.1) - Using `cd` with no arguments

Using `cd` with no argument will return the user to the home directory.

![image](lr1-1.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1`.

![image](lr1-2.png)

This is the expected output because using `cd` with no arguments is meant to return the user to the root directory
This output is not an error.

## 1.2) - Using `ls` with no arguments

Using `ls` with no arguments will list the files / folders in the given path.

![image](lr1-3.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1` which was unchanged by the command.

![image](lr1-4.png)

I got this output because `ls` is meant to list the files / folders in a given path. Since my working directory was in `lecture1`, using `ls` listed all of the files and folders within `lecture1` which were `Hello.class`,  `Hello.java`,  `messages/`, and  `README`.

This output is not an error

## 1.3) - Using `cat` with no arguments

Using `cat` with no arguments will not produce any output immediatly. However, if one enters any text of command afterwards, it will simply return what the user types.

![image](lr1-5.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1` which was unchanged by the command.

![image](lr1-4.png)

After looking up some documentation for the command, `cat` reads from standard input if there are no arguments provided. As I understand it, this is why it returns whatever I type after using the `cat` command.

This output is not an error. It follows exactly what the documentation describes. However, this caveat does not really have a great use for our situation.

## 2.1) - Using `cd` with a directory as an argument

Using `cd` with a directory as an argument will change the users working directory to the one provided as an argument

![image](lr1-6.png)

The absolute path to the working directory before the command was run was:
`/c/Users/noahs/lecture1` which was changed to `/c/Users/noahs/lecture1/messages` by the command.

![image](lr1-4.png)

I got this output because `cd` is used to switch the current working directory to the one provided. Since I provided `messages/` as the argument, the working directory was switched to `/c/Users/noahs/lecture1/messages`.

This is not an error. The command worked exactly as intended.

## 2.2) - Using `ls` with a directory as an argument

Using `ls` with a directory as an argument will list all of the files / folders in the directory.

![image](lr1-7.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1` which was unchanged by the command.

![image](lr1-4.png)

I got this output because `ls` is meant to list the files and folders of the provided path. Since I used `messages` as the argument, the output was the files within `messages` (en-us.txt, .. etc).

This output is not an error.

## 2.3) - Using `cat` with a directory as a argument

Using `cat` with a directory returns the message : `cat: messages: is a directory`.

![image](lr1-8.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1` which was unchanged by the command.

![image](lr1-4.png)

I got this output because `cat` is meant to print the contents of a file. Since a directory was provided, that is something it cannot print, hence the message it gave.

This is infact an error. It is an error because `cat` is supposed to print the contents of a provided file. Since a directory was given rather than a file, that is something `cat` cannot print which is why the error message appeared. It needs a file as an argument to properly run.

## 3.1) - Using `cd` with a file as an argument

Using `cd` with a file as an argument presents the message `bash: cd: README: Not a directory`.

![image](lr1-9.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1` which was unchanged by the command.

![image](lr1-4.png)

I got this output because `cd` is meant to change your working directory. Since the argument provided is a file and not a directory, it cannot switch the working directory to the file.

This output is an error. The command is meant to change directory. Since `README` is not a directory, it produces an error message and does not change anything.

## 3.2) - Using `ls` with a file as an argument

Using `ls` with a file name as an argument simply returns the file name back to the user.

![image](lr1-10.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1` which was unchanged by the command.

![image](lr1-4.png)

I got this output because `ls` is meant to list the files for a given path. Since the path provided is a file, all it does is list the file name.

This output is not an error. The command worked exactly as the documentation states.

## 3.3) - Using `cat` with a file as the argument.

Using `cat` with a file as an argument simply prints the contents of the file.

![image](lr1-11.png)

The absolute path to the working directory before running the command was:
`/c/Users/noahs/lecture1` which was unchanged by the command.

![image](lr1-4.png)

I got this output because `cat` is meant to print the contents of a file given by a path. Since the path I provided is that of a file (`README`), it prints out the contents of the file. 

This output is not an error. `cat` worked exactly as the documentation states.




