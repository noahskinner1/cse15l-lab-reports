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
