# firewall-lab
Basic firewall (ufw) configuration between two Ubuntu VM's in a local virtual network. 

# Devices 
- Host: Windows 10, VirtualBox 7.2.22
- VM1: Ubuntu 25.04, name: UbuntuMain, IP 192.168.56.101
- VM2: Ubuntu 25.04, name: UbuntuSub, IP 192.168.56.102
- Network: Host-Only

# IP check
![ipamain](screenshots/main_ip_a.png)
ip a for Main VM

![ipasub](screenshots/sub_ip_a.jpg)
ip a for Sub VM

![netcheck](screenshots/ping.png)
Successful ping

# SSH installation and setup
![ssh main installed](screenshots/sshmaininstall.png)
Installation for Main VM

![ssh sub installed](screenshots/sshsubinstall.png)
Installation for Sub VM

![ssh successful_installation](screenshots/ssh_successful_connection.png)
Connection established
