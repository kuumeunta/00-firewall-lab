# firewall-lab
Basic firewall (ufw) configuration between two Ubuntu VM's in a local virtual network. 
## Goal
Set up two Ubuntu virtual machines in a local virtual network, connect them via SSH, and configure the ufw firewall on one of them remotely from the other.
## Environment
- Host: Windows 10, VirtualBox 7.2.22
- VM1: Ubuntu 25.04, name: UbuntuMain, IP 192.168.56.101
- VM2: Ubuntu 25.04, name: UbuntuSub, IP 192.168.56.102
- Network: Host-Only

## Network setup
![ipamain](screenshots/main_ip_a.png)
ip a for Main VM
```
ip a
```

---
![ipasub](screenshots/sub_ip_a.jpg)
ip a for Sub VM
```
ip a
```

---
![netcheck](screenshots/ping.png)
Successful ping
```
ping 192.168.56.102
```
## SSH setup
![ssh main installed](screenshots/sshmaininstall.png)
Installation for Main VM
```
sudo apt install openssh-server -y
sudo systemctl status ssh
```

---
![ssh sub installed](screenshots/sshsubinstall.png)
Installation for Sub VM
```
sudo apt install openssh-server -y
sudo systemctl status ssh
```

---
![ssh successful_installation](screenshots/ssh_successful_connection.png)
Connection established
```
ssh vboxuser@192.168.56.102
```
## Firewall (ufw) configuration
![sshconfig](screenshots/sshconfig1.png)
Now on Sub VM allowing SSH in ufw service, then denying all other - except what we allowed firstly.
```
sudo ufw allow ssh
sudo ufw default deny incoming
```

---
![sshconfig](screenshots/sshconfig2.png)
Enabling ufw and checking up actual config
```
sudo ufw enable
sudo ufw status verbose
```
## Testing
![subtestserver](screenshots/subtestserver.png)
Opening :8000 http port on Sub VM and trying to check up connection using curl from Main VM 
```
python3 -m http:server 8000
```
![subtestserver](screenshots/curlport.png)
```
curl --max-time 5 192.168.56.102:8000
```
Connection is denied, so enabling it on Sub VM as well and trying to reconnect 
## Results
## Problems and conclusions
