# COMP-304-Shell-ish-Assignment-1
COMP 304 - Assignment 1

# Overview
This project implements a simple Unix like shell called Shell-ish.


# 1) Part I: Basic Shell Implementation
This implementation of Shell-ish is based on the provided skeleton program. The shell reads user input, parses commands and arguments using whitespace delimiters, and executes the appropriate action for each command.

For commands that are not built-in, the shell creates a child process using fork() and executes the program in the child process, following the process creation model described in Part I – Creating a Child Process.

The shell supports background execution. If a command ends with an ampersand (&), the program is executed in the background and the shell immediately returns the command prompt without waiting for completion.

Program execution is performed using the execv() system call. Since execv() does not automatically resolve executable paths, the shell manually searches each directory listed in the PATH environment variable to locate the command. Both common Linux commands and user programs are supported. The use of execvp() is intentionally avoided to satisfy assignment requirements.

Built-in commands are handled directly by the shell without creating a child process. 