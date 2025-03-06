**Objective**
Familiarisation with Server Message Block or *SMB*.

**Server Message Block**
- It is a communication protocol that provides shared access to files, printers, and serial ports between endpoint on a network. Mostly seen on Windows machines - Windows NT family.
- It is located on port 445.

**Solving The Box**
- Follow directions from [[Meow]] to set up openvpn connection and perform ping check, followed by `nmap -sV` for enumeration of target machine IP.
- Install smbclient using command `sudo apt-get install`.
- List all SMB *shares* located at IP using command `smbclient \\\\{IP address}\\{Sharename}`.
- WorkShares appears human-configured, thus prone to have errors from misconfiguration. Login to this Sharename.
- Use `help` command to list all possible commands in this Sharename.
- Browse directory to locate and retrieve files `WorkNotes.txt` and `flag.txt`. 
- Reveal contents of both to capture all flags. 