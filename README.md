# :desktop_computer: 42Heilbronn :de:

<p align="center">
  <img src="https://github.com/Tilek12/42-project-badges/blob/main/badges/get_next_linem.png">
</p>

<h1 align="center">
 Project - Get Next Line :leftwards_arrow_with_hook:
</h1>

<h2 align="center">
 :white_check_mark: 125/125
</h2>

## :clipboard: Project info: [subject](https://github.com/Tilek12/42Heilbronn-get_next_line/blob/master/.git_docs_get_next_line/en.subject_get_next_line.pdf)

## :green_circle: **Mandatory Part**

**Function name**| get_next_line
|:---|:---|
**Prototype**| char *get_next_line(int fd);
**Turn in files**| get_next_line.c, get_next_line_utils.c, get_next_line.h
**Parameters**| fd: The file descriptor to read from
**Return value**| Read line: correct behavior 
| | NULL: there is nothing else to read, or an error occurred
**External functs.**| read, malloc, free
**Description**| Write a function that returns a line read from a file descriptor

- Repeated calls (e.g., using a loop) to your get_next_line() function should let
you read the text file pointed to by the file descriptor, one line at a time.
- Your function should return the line that was read.
If there is nothing else to read or if an error occurred, it should return NULL.
- Make sure that your function works as expected both when reading a file and when
reading from the standard input.
- Please note that the returned line should include the terminating \n character,
except if the end of file was reached and does not end with a \n character.
- Your header file get_next_line.h must at least contain the prototype of the
get_next_line() function.
- Add all the helper functions you need in the get_next_line_utils.c file.
- Because you will have to read files in get_next_line(), add this option to your
compiler call: -D BUFFER_SIZE=n
It will define the buffer size for read().
The buffer size value will be modified by your peer-evaluators and the Moulinette
in order to test your code.

:warning: **We must be able to compile this project with and without the -D
BUFFER_SIZE flag in addition to the usual flags. You can choose the
default value of your choice.**

- You will compile your code as follows (a buffer size of 42 is used as an example):
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 <files>.c
- We consider that get_next_line() has an undefined behavior if the file pointed to
by the file descriptor changed since the last call whereas read() didn’t reach the
end of file.
- We also consider that get_next_line() has an undefined behavior when reading
a binary file. However, you can implement a logical way to handle this behavior if
you want to.

### :eight_spoked_asterisk: **Forbidden**
- You are not allowed to use your libft in this project.
- lseek() is forbidden.
- Global variables are forbidden.

---------------------------------

## :star: **Bonus part**

### :eight_pointed_black_star: **Here are the bonus part requirements:**
- Develop get_next_line() using only one static variable.
- Your get_next_line() can manage multiple file descriptors at the same time.
For example, if you can read from the file descriptors 3, 4 and 5, you should be
able to read from a different fd per call without losing the reading thread of each
file descriptor or returning a line from another fd.
It means that you should be able to call get_next_line() to read from fd 3, then
fd 4, then 5, then once again 3, once again 4, and so forth.

Append the _bonus.[c\h] suffix to the bonus part files.
It means that, in addition to the mandatory part files, you will turn in the 3 following
files:
- get_next_line_bonus.c
- get_next_line_bonus.h
- get_next_line_utils_bonus.c
