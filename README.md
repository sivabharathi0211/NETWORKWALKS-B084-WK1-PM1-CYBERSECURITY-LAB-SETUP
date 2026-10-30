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
<img width="1225" height="681" alt="Screenshot 2026-10-27 151027" src="https://github.com/user-attachments/assets/baf7d632-2bf5-4403-b8e8-32477ef12866" />

2. Create a NAT Network

Opened VirtualBox Network Manager and created a custom NAT Network with the following settings:

- Name: "NatNetwork"
- IPv4 Prefix: "10.0.0.0/24"
- DHCP: Enabled
- IPv6: Disabled
  <img width="1359" height="718" alt="Screenshot 2026-10-29 194937" src="https://github.com/user-attachments/assets/24f27cd0-1192-41dd-8a8b-55ee6df400b1" />

3. Connect Kali Linux to the NAT Network

Opened the Kali Linux VM settings and configured Adapter 1:

- Attached to: NAT Network
- Name: NatNetwork
<img width="779" height="521" alt="image" src="https://github.com/user-attachments/assets/1b3de229-0975-4de7-b361-43e959876009" />

4. Troubleshoot Network Connectivity

Encountered a network connection issue related to DAD (Duplicate Address Detection) timeout.

Used the following commands to modify and restart the network connection:

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

sudo nmcli connection down "Wired connection 1"

sudo nmcli connection up "Wired connection 1"

<img width="1366" height="643" alt="WhatsApp Image 2026-10-29 at 8 54 03 PM" src="https://github.com/user-attachments/assets/f30aeed8-8dda-479e-bdd1-08119c22065c" />

5. Verify the IP Address

Executed the following command to check the network interface and assigned IP address:

ip addr
<img width="1366" height="643" alt="WhatsApp Image 2026-10-29 at 9 03 47 PM" src="https://github.com/user-attachments/assets/8c4ffba3-a279-4833-a350-f3219f84afc6" />


6. Check the Wired Connection

Verified the wired network connection through Kali Linux Network Settings.
<img width="1366" height="643" alt="WhatsApp Image 2026-10-29 at 9 32 00 PM" src="https://github.com/user-attachments/assets/08018826-e65b-4d1f-a9e7-517ba1996622" />

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

