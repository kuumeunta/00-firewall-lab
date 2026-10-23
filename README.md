# firewall-lab
Basic firewall (ufw) configuration between two Ubuntu VM's in a local virtual network. 
# Goal
Set up two Ubuntu virtual machines in a local virtual network, connect them via SSH, and configure the ufw firewall on one of them remotely from the other.
# Environment
- Host: Windows 10, VirtualBox 7.2.22
- VM1: Ubuntu 25.04, name: UbuntuMain, IP 192.168.56.101
- VM2: Ubuntu 25.04, name: UbuntuSub, IP 192.168.56.102
- Network: Host-Only

# Network setup
![ipamain](screenshots/main_ip_a.png)
```
ip a
```
ip a for Main VM

![ipasub](screenshots/sub_ip_a.jpg)
```
ip a
```
ip a for Sub VM

![netcheck](screenshots/ping.png)
```
ping 192.168.56.102
```
Successful ping

# SSH setup
![ssh main installed](screenshots/sshmaininstall.png)
```
sudo apt install openssh-server -y
sudo systemctl status ssh
```
Installation for Main VM

![ssh sub installed](screenshots/sshsubinstall.png)
```
sudo apt install openssh-server -y
sudo systemctl status ssh
```
Installation for Sub VM

![ssh successful_installation](screenshots/ssh_successful_connection.png)
```
ssh vboxuser@192.168.56.102
```
Connection established

## Firewall (ufw) configuration
## Results
## Problems and conclusions
