
# Deployment Script and CRON Job Setup

## Pre-requisites

### Create 2 VM servers

1. Set up two virtual machines (VM1 and VM2) for your server and client sides.

### Install Apache2 on VM2 (Server Side)

```bash
sudo apt-get update -y
sudo apt-get upgrade -y
sudo apt-get install apache2 -y
```

## Main Task

### Set Up SSH Keys on Client Side (VM1)

```bash
ssh-keygen -t rsa -b 4096
ssh-copy-id server@ip
ssh server@ip
```

### Create Website Content (Index File)

```bash
nano index.html
```
Add your website content to the `index.html` file and save it.

### Create Deployment Script

```bash
nano script.sh
```
Add the following content to `script.sh`:

```bash
#!/bin/bash
ssh mustan@192.168.222.135 "sudo service apache2 stop"
echo "Service STOPPED"
scp /home/mustanali/Desktop/index.html mustan@192.168.222.135:/var/www/html/
echo "File Copied"
ssh mustan@192.168.222.135 "sudo service apache2 restart"
echo "Service STARTED"
```

### Make the Script Executable

```bash
chmod +x script.sh
```

### Schedule as a CRON Job

Add the following line to your crontab to run the script every Sunday at 4 AM:

```bash
0 4 * * 7 /home/mustanali/Desktop/script.sh
```

This CRON expression breaks down as follows: `minute (0) hour (4) day-of-month (*) month (*) day-of-week (7)`.

## Explanation

- **Update and Upgrade:**
  Update and upgrade your package repositories to ensure you have the latest package information.

- **Install Apache2:**
  Install Apache2 on VM2, which is the server side.

- **SSH Key Generation:**
  Generate SSH keys on VM1 (client side) for secure communication with VM2.

- **Copy SSH Key:**
  Copy the public SSH key to VM2 to enable passwordless SSH login.

- **SSH Connection Test:**
  Test SSH connection to ensure passwordless login is working.

- **Create Index File:**
  Use a text editor (e.g., nano) to create the `index.html` file for your website content.

- **Create Deployment Script:**
  Use a text editor to create the deployment script (`script.sh`) that stops Apache, copies the new content, and restarts Apache.

- **Make Script Executable:**
  Ensure the script is executable by running `chmod +x script.sh`.

- **Schedule as CRON Job:**
  Schedule the deployment script as a CRON job to run every Sunday at 4 AM.

Ensure to adjust paths and server details based on your actual setup.
```
