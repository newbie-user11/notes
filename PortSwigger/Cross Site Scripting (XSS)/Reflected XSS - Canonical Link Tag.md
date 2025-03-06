*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Calling alert function following user input:
- *Alt+Shift+x* on Windows
- *Ctrl+Alt+x* on MacOS
- *Alt+x* on Linux

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- URL for setting access key to navigate across page.

**Barrier to entry** 
- User input.

**Bypassing Barrier to Entry**
- Getting user to use the *x* key for triggering exploit.

**Template Exploit**
`https://YOUR-LAB-ID.web-security-academy.net/?%27accesskey=%27x%27onclick=%27alert(1)`

