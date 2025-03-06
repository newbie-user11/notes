**Objective**
Familiarisation with *File Transfer Protocol* or FTP.

**File Transfer Protocol**
- FTP is a communication protocol for transferring files between computers on a network.
- It uses a client-server model with separate connections for control and data.
- Users typically log in with a username and password, but anonymous access may be possible.
- Secure FTP or SFTP is encrypted for security against anonymous access.

**Solving The Box**
- Follow directions from [[Meow]] to set up openvpn connection and perform ping check, followed by `nmap -sV` for enumeration.
- `nmap` reveals that the open port uses FTP. Use ftp command, then login as *anonymous* with password *anon123*.
- Once inside, use `ls` command to find flag.txt. 
- As `cat` does not work on port, use `get` to retrieve the flag file from port then `bye` to exit port.
- Use `ls` again to confirm that flag.txt is in our working directory. Now use `cat` to *capture the flag* - 035db21c881520061c53e0536e44f815.

**Bonus Information**
- `help` command reveals all allowed commands on port. `man` followed by command name opens its manual page.

