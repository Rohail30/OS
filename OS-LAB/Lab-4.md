# Linux Command Cheat Sheet

## `|` - Pipe Operator
The pipe operator (`|`) takes the output of the command on the left and pipes it as input to the command on the right. It allows for the seamless flow of data between commands.

### Examples:
* `cat script.sh | head` - Displays the first 10 lines of a script by piping the output of `cat` to `head`.
* `man man | less` - Shows the manual page of a command in a page-by-page manner by piping the output of `man` to `less`.
* `cat file.txt | grep "hello"` - Searches for the string "hello" in the content of the file by piping the output of `cat` to `grep`.

## `grep` - Search for a String in a File
The `grep` command is used to search for a specified string or pattern in a file or stream of text.

### Examples:
* `echo "hello world" | grep "hello"` - Searches for the string "hello" in the provided text.
* `cat file.txt | grep "hello"` - Searches for the string "hello" in the content of the file by piping the output of `cat` to `grep`.
* `grep "hello" file.txt` - Searches for the string "hello" in the content of the file and displays the line containing the string.

