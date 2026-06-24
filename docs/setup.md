To begin, I created boith a windows client and a windows server VM.

### VMWare Network

I used VMNet2 and gave it the ip 192.168.200.0 with a 255.255.255.0 subnet mask.

### Server Setup and Install

First, I went into settings and changed from DHCP to configure my IP to manual, using IPv4. I set the address to 192.168.200.10 with a subnet mask of 255.255.255.0. (See setup/IP-Config)

Second, I changed the server name to DC01, shorthand for being the first Domain Controller. I had to restart to make this change take affect.

Now, using the Server Manager, I installed the Active Directory Domain Services. A DNS server was also installed during this step. (See setup/Active-Directory-DNS-Install.png)

After install, i was prompted to promote this server to a domain controller (see setup/Set-up-Domain-Controller.png). I selected add an new forest with a root domain called cyber.lab (see setup/new-forst-cyber.lab.png)

Next, you will be prompted to create a DSRM passsword. After that, I recieved a warning about DNS Delegation not being created. i ignored this for now. My NetBIOS name was CYBER.

I was prompted with and error on a prerequisteete when trying to execute. Windows wants me to set a password for the local Administrator account after it made that account the new Domain Administrator account. I ran a comand as administrator, net user Administrator * then entered the password i wanted to set twice. After that, i refreshed and could install. I had some warnings but ignored them to finish the config later.

After restart, i saw CYBER/steve as the new local administrator. This is good. It shows that the server now sees the Domain Admin as the local admin.

### AD Setup

After the above steps, I verified my Active Directory setup by going to Server Manager -> Tools -> Active Directory Users and Computers. I expanded my cyber.lab and saw Builtin, Computers, etc. (see setup/AD-Setup/verify-users-computers)

I took a second here to make some differentiation between the two connections I have, the VMNet and the internet. (See setup/AD-Setup/NAT-Edit.png). To navigate here, I did Win + R, serached for ncpa.cpl, selected the ethernet that connected to the internet, double clicked Internet Protocol Version 4, went into advanced, selected the DNS tab, and deselected the bottom option "Register this connection's address in DNS.

After this, I navigated back to the Active Directory Users and Computers. I ten stared to Creat OUs, or Organizational Units, for the homelab.