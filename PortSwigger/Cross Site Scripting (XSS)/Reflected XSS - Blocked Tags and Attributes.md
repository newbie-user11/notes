*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective:** Calling print function in web browser without user interaction.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- GET search request

**Barrier to entry** 
- HTML tags are blocked in search function. Determined by injecting `<img src=1 onerror=print()>`.

**Bypassing Barrier to Entry**
- Send GET search request to Burp Intruder.
- Replace search term with `<>` and set payload between `<>`. 
- Set payload between `<>`. For payload, refer [link](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet.
- Attack returns a 200 response for HTML tag `body` unlike a 400 response for most other tags.
- Reset search term as `<body%20=1>` and set payload position between 20 and =.

**Template Exploit**
`<iframe src="https://YOUR-LAB-ID.web-security-academy.net/?search=%22%3E%3Cbody%20onresize=print()%3E" onload=this.style.width='100px'>`


