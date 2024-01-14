# Linux Command Cheat Sheet

## Table of Contents

1. **UFW (Uncomplicated Firewall) Commands**
   - `sudo apt-get install ufw` - Install the firewall
   - `sudo ufw enable` / `sudo ufw disable` - Enable/Disable the firewall
   - `sudo ufw status` - Check the status of the firewall
   - `sudo ufw allow 22` - Allow port 22

2. **Network Configuration Commands**
   - `ip addr` - Show IP addresses of all network interfaces
   - `ip addr show ens33` - Show IP address of a specific network interface
   - `ip route` - Show routing table
   - `sudo lshw -class network` - Show network hardware information
   - `cat /etc/netplan/01-netcfg.yaml` - Network configuration file
   - ```yaml
     network:
       version: 2
       renderer: networkd
       ethernets:
         ens33:  
           addresses:
             - 192.168.1.100/24  
           routes:
             - to: 0.0.0.0/0  
               via: 192.168.1.1  
           nameservers:
             addresses: [8.8.8.8, 8.8.4.4]
     ```
   - `sudo netplan apply` - Apply the network configuration
   - `sudo netplan --debug apply` - Apply the network configuration with debug information
   - `sudo ip addr flush ens33` - Flush the IP address of a specific network interface

**Note:** Replace `ens33` with the appropriate network interface name used in your system.

# Netplan configuration for network settings

```yaml
network:
  version: 2
  renderer: networkd
  
  # Ethernet interfaces configuration
  ethernets:
    ens33:  # Interface name (use 'ip addr' command to find your interface name)
      addresses:
        - 192.168.1.100/24  # IP address and subnet mask (e.g., ip addr)
      routes:
        - to: 0.0.0.0/0  # Default route
          via: 192.168.1.1  # Gateway IP address (e.g., ip route)
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]  # DNS servers (replace with your DNS servers)
