Kali Linux Lab – VirtualBox NAT Network Setup

📌 About the Project

This project documents how I created a small virtual networking lab using Oracle VirtualBox and Kali Linux.

The main goal was to configure a custom NAT Network in VirtualBox, connect my Kali Linux virtual machine to it, and establish network connectivity using NetworkManager commands.

This practical helped me understand how virtual machines communicate through a NAT Network and how to troubleshoot basic network connection issues in Kali Linux.

🎯 Objectives

- Install and configure Oracle VirtualBox.
- Create a custom NAT Network.
- Connect Kali Linux to the configured network.
- Configure network settings using "nmcli".
- Troubleshoot connection issues.
- Verify the assigned IP address.

🛠️ Tools & Technologies

- Kali Linux – Operating system for the virtual lab.
- Oracle VirtualBox – Virtualization software.
- 7-Zip – File extraction utility.
- NetworkManager (nmcli) – Network configuration tool.

🌐 Network Configuration

Configuration| Details
Network Type| NAT Network
Network Name| NatNetwork
IPv4 Prefix| 10.0.0.0/24
DHCP| Enabled
IPv6| Disabled
Virtual Machine| Kali Linux

⚙️ Implementation Steps

1. Install the Required Tools

Installed Oracle VirtualBox and 7-Zip to prepare the virtual lab environment.

2. Create a NAT Network

Opened VirtualBox Network Manager and created a custom NAT Network with the following settings:

- Name: "NatNetwork"
- IPv4 Prefix: "10.0.0.0/24"
- DHCP: Enabled
- IPv6: Disabled

3. Connect Kali Linux to the NAT Network

Opened the Kali Linux VM settings and configured Adapter 1:

- Attached to: NAT Network
- Name: NatNetwork

4. Troubleshoot Network Connectivity

Encountered a network connection issue related to DAD (Duplicate Address Detection) timeout.

Used the following commands to modify and restart the network connection:

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

sudo nmcli connection down "Wired connection 1"

sudo nmcli connection up "Wired connection 1"

5. Verify the IP Address

Executed the following command to check the network interface and assigned IP address:

ip addr

6. Check the Wired Connection

Verified the wired network connection through Kali Linux Network Settings.

📚 What I Learned

Through this hands-on lab, I gained practical experience in:

- Setting up virtual networking environments.
- Understanding NAT Network configuration.
- Connecting virtual machines to custom networks.
- Using Linux commands for network management.
- Identifying and troubleshooting network connectivity issues.
- Checking IP addresses and network interfaces.

⚠️ Disclaimer

This lab was created for educational purposes and personal cybersecurity learning. All networking experiments should be performed in authorized lab environments.

