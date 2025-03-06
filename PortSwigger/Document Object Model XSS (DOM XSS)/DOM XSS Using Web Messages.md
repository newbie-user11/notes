*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Call print function by delivering exploit through Document Object Model or web application HTML code.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- Response to home page GET request includes `addEventListener()`, which listens for web messages. 
- This is the point of entry for our message to trigger print function.

**Mechanism of Exploit** 
- Use iframe to deliver exploit triggering print() function.

**Template**
`<iframe src="https://0ae700bd04f8f05580001ced00180013.web-security-academy.net/" onload="this.contentWindow.postMessage('<img src=1 onerror=print()>','*')">`



