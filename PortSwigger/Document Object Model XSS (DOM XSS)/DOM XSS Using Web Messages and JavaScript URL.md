*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Call print function by delivering exploit through Document Object Model or web application HTML code.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- Response to home page GET request includes `addEventListener()`, which listens for web messages. 
- This is the point of entry for our message to trigger print function.

**Barrier to Entry**
- See further within the `<script>` tag that `indexOf()` checks for `http:` or `https:`. Payload needs to include either one of the two.

**Mechanism of Exploit** 
- On match, the request is sent to `location.href` sink where commands are converted to output.
- Use iframe to deliver exploit triggering print() function.

**Template**
`<iframe src="https://YOUR-LAB-ID.web-security-academy.net/" onload="this.contentWindow.postMessage('javascript:print()//http:','*')">`


