*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Reveal HTTPS and DNS requests initiated by the web application.

**Blind SSRF**
- Blind Server Side Request Forgery (SSRF) occurs when a server side request is forged by attacker. 
- The response remains server side and is not returned user side, being fully backend.

**Point of Entry**
- Open any product on ecommerce website and intercept its associated GET product request.
- The Referer header is our point of entry.

**Exploit for Entry**
- Send GET product request to repeater and replace Referer header domain with a Collaborator payload - for shortcut use right click. 
- Send request. Check Collaborator Poll for updates.

