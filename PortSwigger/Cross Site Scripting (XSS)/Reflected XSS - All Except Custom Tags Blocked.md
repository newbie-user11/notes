*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective:** Calling alert function through `document.cookie` without user interaction.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- GET search request

**Barrier to entry** 
- HTML tags are blocked except custom ones.

**Bypassing Barrier to Entry**
- Send GET search request to Burp Intruder, and replace search term with `<>`.
- Set payload between `<>`. For payload, refer [[https://portswigger.net/web-security/cross-site-scripting/cheat-sheet]]
- Attack returns a 200 response for HTML tag `body` unlike a 400 response for most other tags.
- Reset search term as `<body%20=1>` and set payload position between 20 and =.

**Template Exploit**
`<script> location = 'https://YOUR-LAB-ID.web-security-academy.net/?search=%3Cxss+id%3Dx+onfocus%3Dalert%28document.cookie%29%20tabindex=1%3E#x'; </script>`


