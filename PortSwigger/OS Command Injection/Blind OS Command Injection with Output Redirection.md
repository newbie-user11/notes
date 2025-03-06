**Objective**
Execute the `whoami` command to identify the current user.

**OS Command Injection**
- An attacker is able to compromise a web application by targeting the server hosting it, using OS commands. For instance, UNIX commands for UNIX-like based servers.
- This attack is also called *shell injection*.
- *Blind* OS command injection is executed where no output is returned in response to a request.

**Point of Entry**
*Submit Feedback* form.

**Execution**
- Start intercept, fill the feedback form with random values then submit the form.
- In the issued POST request, replace email parameter with the payload including `whoami` command. The command's output is sent to the file path specified in payload. 
- Forward request and stop intercepting. Go to home and start intercepting, then open any blogpost. 
- In the generated POST request, replace the value of the filename parameter with `output.txt`. Forward request.
- The response shows current user information.

**Exploit Payload**
`email=||whoami>/var/www/images/output.txt`