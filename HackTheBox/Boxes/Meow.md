**Objective**
To set up a vpn connection for Enumeration, or learning as much as possible about the target. Then capturing the flag file.

**VPN Connection**
- In Kali virtual machine, open and login to Hack The Box (HTB). Click on *Starting Point* > *Meow*. Download openVPN file for the *Meow* box.
- Open a kali terminal and change working directory to where the downloaded file is using `cd` command.
- As superuser, start openVPN using the command `sudo openvpn` followed by file name with extension. On success, *Initialisation Sequence Completed* is received in response. OpenVPN is set up.
- Open another terminal window and send `ping` request to IP mentioned on HTB. `ping` is called an Internet Connection Message Protocol (ICMP) echo request. After a few consistent responses, press *ctrl + c* to end the command. 
- Ping confirms whether network packets being sent are received by the destination to check connection stability.

**Enumeration**
Every server uses ports. These ports are for serving data to clients. We will use nmap to scan the ports to check if they are open or closed.
- Execute command `sudo nmap -sV`, where `-sV` is called service detection flag. This flag determines the name and function of identified services. 
- Response indicates open port `23/tcp` running `telnet` service protocol. Telnet stands for Teletype Network and operates on the client/server principle. It is for remote management of other hosts on a network.
- Access the open port using command `telnet` following the box IP address.
- Enter username *root* for login. Then enter command `ls` to locate *flag.txt*. Open the file using `cat` command to reveal its contents - b40abdfe23665f766f9c61ecba8a4c19.


