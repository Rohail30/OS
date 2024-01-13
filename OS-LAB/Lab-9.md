# SSH and SCP Cheat Sheet

## Generate SSH Key Pair (Client Side)

```bash
ssh-keygen -t rsa -b 4096
```

Generates a new SSH key pair. The `-t` option specifies the type (rsa), and the `-b` option specifies the number of bits (4096).

## Install OpenSSH Service (Server Side)

```bash
sudo apt-get install openssh-server
sudo systemctl status ssh.socket
sudo systemctl status ssh.service
sudo systemctl restart ssh.service
```

Installs the OpenSSH server on the server side. The subsequent commands check the status of the SSH socket and service, and restart the service if necessary.

## Copy SSH Public Key to Server (Client Side)

```bash
ssh-copy-id server_username@server_ip_address
```

Copies the public key to the server, allowing for passwordless authentication.

## Login to the Server (Client Side)

```bash
ssh server_username@server_ip_address
```

Logs in to the server using SSH.

## Copy File to Server using SCP (Client Side)

```bash
scp fileToCopy.txt server_username@server_ip_address:directoryToCopyTo
```

Copies a file from the local machine to the server using SCP.

## Download File from Server using SCP (Client Side)

```bash
scp server_username@server_ip_address:fileToDownload.txt directoryToDownloadTo
```

Downloads a file from the server to the local machine using SCP.

```
