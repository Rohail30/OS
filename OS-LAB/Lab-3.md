# Linux Command Cheat Sheet

## `date`
Displays the current date and time on the terminal. Useful for checking the system clock.

## `cal` and `cal 2023`
Shows the calendar of the current month or a specific year (in this case, 2023). Helpful for quick reference to dates.

## `clear`
Clears the terminal screen, providing a clean slate for new commands and output.

## `sleep 5`
Introduces a delay of 5 seconds in command execution. Useful for scheduling or introducing pauses in script execution.

## `time sleep 2`
Measures and displays the time taken to execute a command. Helpful for performance analysis.

## `which bash`
Shows the full path of the executable for the specified command (in this case, "bash"). Useful for locating the source of a command.

## `whereis bash`
Provides information on the location of the specified command ("bash"). Unlike `which`, it lists all occurrences of the executable in Linux directories.

## `alias c='clear'` and `unalias c`
Creates an alias "c" for the `clear` command, allowing a custom shorthand. The second command removes the alias, reverting to the original command.

## `history`
Displays a list of previously executed commands, aiding in recalling and reusing commands.

## `df`
Shows disk usage information, providing details on available and used space on mounted filesystems.

## `shutdown` and `reboot`
Commands to shut down or restart the system, respectively. Ensures a safe and controlled system shutdown or restart.

## `cat file.txt`
Displays the content of a text file named "file.txt" on the terminal.

### `cat > file.txt`
Allows the user to input text from the keyboard and save it to "file.txt."

### `cat file1.txt > file2.txt`
Copies the content of "file1.txt" to "file2.txt," overwriting the contents of the latter.

### `cat file1.txt >> file2.txt`
Appends the content of "file1.txt" to the end of "file2.txt."

### `cat file1.txt file2.txt > file3.txt`
Merges the contents of "file1.txt" and "file2.txt" into a new file named "file3.txt."

## `head file.txt`
Displays the first 10 lines of a text file named "file.txt."

## `tail file.txt`
Displays the last 10 lines of a text file named "file.txt."

## `more file.txt` and `less file.txt`
Commands for viewing the content of a file page by page, facilitating the reading of large files.

## `cp file1.txt file2.txt` and `cp file1.txt /myfolder/file2.txt`
Copies the content of "file1.txt" to "file2.txt" or to a specified directory ("/myfolder").

## `mv file1.txt file2.txt` and `mv file1.txt /myfolder/file2.txt`
Moves "file1.txt" to "file2.txt" or to a specified directory ("/myfolder").

## `rmdir myfolder`
Deletes an empty directory named "myfolder."

## `find . -name file.txt` and `find /home/user -name file.txt`
Searches for a file named "file.txt" in the current directory or a specified directory ("/home/user").

