# CSCL 2205 Lab: Operating Systems
This course is designed for beginners seeking to enhance their understanding of the Linux operating system and command-line interface (CLI). Through a series of practical lessons, participants will acquire fundamental skills to navigate the Linux file system, perform essential file and directory operations, and manage system configurations.
<h2>Assignment</h2>
<details>
<p>Main Task:
Create a deployment script that utilizes SSH to connect to a remote Apache server(VM2), stops the Apache service, deploys a new website content from a local directory(VM1) to the server(VM2), and restarts the Apache service. Schedule this deployment script as a CRON job to run every Sunday at 4 AM.</p>
</details>
<h2>Lab-2</h2>
<details>

- `sudo`
- `init 3`
- `runlevel`
- `pwd`
- `cd /myfolder`
- `cd ..`
- `cd /`
- `cd ~`
- `mkdir myfolder`
- `touch myfile.txt`
- `nano myfile.txt`
- `rm myfile.txt`
- `ls`
- `man mkdir`
- `clear`
- `whoami`
- `passwd`
- `exit`


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
<h2>Lab-7</h2>
<details>

1. **Function Declaration**
2. **IF / ELSE Statement**
3. **FOR Loop (Printing Array Elements)**
4. **WHILE Loop (Printing Numbers from 1 to 10)**

</details>
<h2>Lab-8</h2>
<details>

### Process Management:

- **Process:**
  - Foreground and background process explanation.

- **Process Attributes:**
  - UID, PID, PPID, TTY, CMD, STIME, TIME, C.

- **Managing Processes:**
  - pwd &, ps, kill.

- **Linux Scheduler:**
  - Preemptive and Non-Preemptive Scheduler.

### Short Job First (SJF) - Script Example:

- Script that implements the Shortest Job First (SJF) scheduling algorithm.
</details>
<h2>Lab-9</h2>
<details>
  
- **Generate SSH Key Pair (Client Side):**
  - `ssh-keygen -t rsa -b 4096`

- **Install OpenSSH Service (Server Side):**
  - `sudo apt-get install openssh-server`
  - `sudo systemctl status ssh.socket`
  - `sudo systemctl status ssh.service`
  - `sudo systemctl restart ssh.service`

- **Copy SSH Public Key to Server (Client Side):**
  - `ssh-copy-id server_username@server_ip_address`

- **Login to the Server (Client Side):**
  - `ssh server_username@server_ip_address`

- **Copy File to Server using SCP (Client Side):**
  - `scp fileToCopy.txt server_username@server_ip_address:directoryToCopyTo`

- **Download File from Server using SCP (Client Side):**
  - `scp server_username@server_ip_address:fileToDownload.txt directoryToDownloadTo`

</details>
<h2>Lab-10</h2>
<details>
  
1. **Cron Installation and Configuration**
   - `sudo apt install cron` - Install cron
   - `sudo systemctl enable cron` - Enable cron

2. **Cron Job Syntax**
   - `@yearly script.sh` or `0 0 1 1 * script.sh` - Run once a year
   - `@monthly script.sh` or `0 0 1 * * script.sh` - Run once a month
   - `@weekly script.sh` or `0 0 * * 0 script.sh` - Run once a week
   - `@daily script.sh` or `0 0 * * * script.sh` - Run once a day
   - `@hourly script.sh` or `0 * * * * script.sh` - Run once an hour
   - `@reboot script.sh` - Run once at startup

3. **Managing Cron Jobs**
   - `crontab -e` - Edit cron jobs
   - `crontab -l` - List cron jobs
   - `crontab -r` - Remove all cron jobs
</details>
<h2>Lab-11</h2>
<details>

1. **UFW (Uncomplicated Firewall) Commands**
2. **Network Configuration Commands**
</details>
