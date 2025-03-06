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
- See further within the `<script>` tag that `JSON.parse()` checks for `type`, and `load-channel` under `switch` changes `iframe src` attribute.
- Payload needs to include either oane of the two.

**Mechanism of Exploit** 
- Use iframe to deliver exploit triggering print() function.
- The message of the payload is sent to home page via `ACMEplayer.element`. This element has its `src` or *source* set as our payload.

**Template**
`<iframe src=https://YOUR-LAB-ID.web-security-academy.net/ onload='this.contentWindow.postMessage("{\"type\":\"load-channel\",\"url\":\"javascript:print()\"}","*")'>
`


