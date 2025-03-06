*This information is only for the purposes of education and skills development.*

**XSS**
- In Cross Site Scripting, malicious JavaScript payload is injected across different sites within the same website. 
- OWASP suggests calling it *code injection* for simplicity.
- As the attack occurs in the user's browser session, it is client side instead of server side.

**Point of Entry**
- Vulnerable DOM or Document Object Model, which is the HTML code of the web application shown in request response.
- HTML code `storeId=` allows product stock check function by location, and is vulnerable to XSS.
- The value of `storeId=` can be altered through the webpage URL. This is the entry point for our exploit.

**Barrier to entry** 
Breaking the html code to trigger the JavaScript exploit. 

**Bypassing Barrier to Entry**
Starting our payload with a " to break the webpage HTML code. This ensures that the exploit is executed.

**Template**
`product?productId=1&storeId="></select><img%20src=1%20onerror=alert(1)>`


