
# Deployment Script and CRON Job Setup

## Pre-requisites

### Create 2 VM servers (Server Side)

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
ssh-keygen -t rsa -b 4096        # (Client Side)
ssh-copy-id server@ip            # (Client Side)
ssh server@ip                    # (Client Side)
```

### Create Website Content (Index File) (Client Side)

```bash
nano index.html                  # (Client Side)
```
Add your website content to the `index.html` file and save it.

### Create Deployment Script (Client Side)

```bash
nano script.sh                   # (Client Side)
```
Add the following content to `script.sh`:

```bash
#!/bin/bash
ssh mustan@192.168.222.135 "sudo service apache2 stop"                 # (Client Side)
echo "Service STOPPED"
scp /home/mustanali/Desktop/index.html mustan@192.168.222.135:/var/www/html/    # (Client Side)
echo "File Copied"
ssh mustan@192.168.222.135 "sudo service apache2 restart"              # (Client Side)
echo "Service STARTED"
```

### Make the Script Executable (Client Side)

```bash
chmod +x script.sh               # (Client Side)
```

### Schedule as a CRON Job (Client Side)

Add the following line to your crontab to run the script every Sunday at 4 AM:

```bash
0 4 * * 7 /home/mustanali/Desktop/script.sh           # (Client Side)
```

This CRON expression breaks down as follows: `minute (0) hour (4) day-of-month (*) month (*) day-of-week (7)`.

## Explanation

- **Update and Upgrade:** (Server Side)
  Update and upgrade your package repositories to ensure you have the latest package information.

- **Install Apache2:** (Server Side)
  Install Apache2 on VM2, which is the server side.

- **SSH Key Generation:** (Client Side)
  Generate SSH keys on VM1 (client side) for secure communication with VM2.

- **Copy SSH Key:** (Client Side)
  Copy the public SSH key to VM2 to enable passwordless SSH login.

- **SSH Connection Test:** (Client Side)
  Test SSH connection to ensure passwordless login is working.

- **Create Index File:** (Client Side)
  Use a text editor (e.g., nano) to create the `index.html` file for your website content.

- **Create Deployment Script:** (Client Side)
  Use a text editor to create the deployment script (`script.sh`) that stops Apache, copies the new content, and restarts Apache.

- **Make Script Executable:** (Client Side)
  Ensure the script is executable by running `chmod +x script.sh`.

- **Schedule as CRON Job:** (Client Side)
  Schedule the deployment script as a CRON job to run every Sunday at 4 AM.

Ensure to adjust paths and server details based on your actual setup.
```
