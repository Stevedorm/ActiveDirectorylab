To begin, I created boith a windows client and a windows server VM.

### VMWare Network

I used VMNet2 and gave it the ip 192.168.200.0 with a 255.255.255.0 subnet mask.

### Server Setup - AD

First, I went into settings and changed from DHCP to configure my IP to manual, using IPv4. I set the address to 192.168.200.10 with a subnet mask of 255.255.255.0. (See setup/Windows-server-ip-config.png)

Second, I changed the server name to DC01, shorthand for being the first Domain Controller. I had to restart to make this change take affect.

Now, using the Server Manager, I installed the Active Directory Domain Services. A DNS server was also installed during this step. (See setup/Active-Directory-DNS-Install.png)