*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*
**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- POST request for comment includes comment element in body. 
- This is a vulnerability that can be used as point of entry into DOM or Document Object Model.

**Barrier to entry** 
- Comment input encoding using `replace()` function to protect against XSS. 
- Angle brackets enclosing the payload being replaced with alphanumeric values disables the exploit.
- `<img src=1 onerror=alert(1)>` becomes `%3Cimg+src%3D1+onerror%3Dalert%281%29%3E`

**Bypassing Barrier to Entry**
- Starting payload with `<>` bypasses encoding as it signals that comment requiring encoding has ended.
- If a JavaScript payload follows `<>` it will not be encoded and will execute. 

**Template Payload**
``<><img src=1 onerror=alert(1)>``


