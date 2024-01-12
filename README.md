# OS-LAB
This course is designed for beginners seeking to enhance their understanding of the Linux operating system and command-line interface (CLI). Through a series of practical lessons, participants will acquire fundamental skills to navigate the Linux file system, perform essential file and directory operations, and manage system configurations.
<h2>Lab-2</h2>
<details>
- sudo
- init 3
- runlevel
- pwd
- cd /myfolder
- cd ..
- cd /
- cd ~
- mkdir myfolder
- touch myfile.txt
- nano myfile.txt
- rm myfile.txt
- ls
- man mkdir
- clear
- whoami
- passwd
- exit
</details>
<h2>Lab-3</h2>
<details>
- `date`
- `cal` and `cal 2023`
- `clear`
- `sleep 5`
- `time sleep 2`
- `which bash`
- `whereis bash`
- `alias c='clear'` and `unalias c`
- `history`
- `df`
- `shutdown` and `reboot`
- `cat file.txt`
  - `cat > file.txt`
  - `cat file1.txt > file2.txt`
  - `cat file1.txt >> file2.txt`
  - `cat file1.txt file2.txt > file3.txt`
- `head file.txt`
- `tail file.txt`
- `more file.txt` and `less file.txt`
- `cp file1.txt file2.txt` and `cp file1.txt /myfolder/file2.txt`
- `mv file1.txt file2.txt` and `mv file1.txt /myfolder/file2.txt`
- `rmdir myfolder`
- `find . -name file.txt` and `find /home/user -name file.txt`
</details>
<h2>Lab-4</h2>
<details>
- `|` - Pipe Operator
  - `cat script.sh | head`
  - `man man | less`
  - `file.txt | grep "hello"`
- `grep` - Search for a String in a File
  - `echo "hello world" | grep "hello"`
  - `cat file.txt | grep "hello"`
  - `grep "hello" file.txt`
</details>
<h2>Lab-5</h2>
<details>
- cat /etc/passwd
- cat /etc/group

User Management:
- sudo adduser testuser
- sudo deluser testuser
- sudo passwd testuser
- su -l testuser
- sudo usermod -aG sudo testuser

Group Management:
- sudo groupadd testgroup
- sudo groupdel testgroup
- sudo usermod -aG testgroup testuser
- sudo gpasswd -d testuser testgroup

File and Directory Permissions:
- ls -l

Linux Permissions Annotations:
- r - Read
- w - Write
- x - Execute
- - - No permission
- 1 - Execute only
- 2 - Write only
- 3 - Write and execute
- 4 - Read only
- 5 - Read and execute
- 6 - Read and write
- 7 - Read, write, and execute
- u - User
- g - Group
- o - Others
- a - All

Changing Permissions:
- chmod 777 myfile.txt
- chmod o+w myfile.txt
- chmod g-xw myfile.txt

Changing Ownership:
- chown testuser myfile.txt
- chown :testgroup myfile.txt
- chown testuser:testgroup myfile.txt
- chown -R testuser:testgroup myfolder
</details>
<h2>Lab-6</h2>
<details>
- nano script.sh
- chmod +x script.sh
- ./script.sh
- bash script.sh

Basics of Scripting:
- #! /bin/bash
- echo "Hello World"
- echo -e "Hello\nWorld"
- myVar="Hello World"
- echo $myVar

Reading Input from User:
- read
- read myVar
- read myVar1 myVar2 myVar3
- read -a myVar

Array Definition:
- arr[]
- arr=(1 2 3)
- arr[0]=1

Array Operations:
- echo ${arr[0]} ${arr[1]}
- echo ${#arr[@]}

For Loop Syntax (Printing Array Elements):
- for (( i=0; i<${#arr[@]}; i++ )); do
    echo ${arr[$i]}
  done
</details>
