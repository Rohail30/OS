# Bash Scripting Cheat Sheet

## Creating and Running a Script:

* **`nano script.sh`** - Creates a script file using the Nano text editor.
* **`chmod +x script.sh`** - Grants execute permissions to the script file.

### Methods to Run a Script File:

* `./script.sh` - Executes the script directly.
* `bash script.sh` - Executes the script using the Bash interpreter.

## Basics of Scripting:

* **`#! /bin/bash`** - Shebang line to specify the interpreter (Bash, in this case).
* **`echo "Hello World"`** - Prints a message to the terminal.
* **`echo -e "Hello\nWorld"`** - Prints a message with a new line (use `-e` to enable escape characters).
* **`myVar="Hello World"`** - Creates a variable and assigns a value.
* **`echo $myVar`** - Prints the value of a variable.

## Reading Input from User:

* **`read`** - Reads a value from the user and assigns it to the default variable `REPLY`.
* **`read myVar`** - Reads a value from the user and assigns it to a variable.
* **`read myVar1 myVar2 myVar3`** - Reads 3 values from the user and assigns them to 3 variables.
* **`read -a myVar`** - Reads a value from the user, separated by space, and assigns it to an array.

## Array Definition:

* `arr[]` - Creates an empty array.
* `arr=(1 2 3)` - Creates an array with values.
* `arr[0]=1` - Creates an array and assigns a value to an element.

## Array Operations:

* **`echo ${arr[0]} ${arr[1]}`** - Prints the value of specific elements in an array.
* **`echo ${#arr[@]}`** - Prints the length of an array.

## For Loop Syntax (Printing Array Elements):

```bash
for (( i=0; i<${#arr[@]}; i++ )); do
    echo ${arr[$i]}
done
