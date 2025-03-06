*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Call print function in user session.

**DOM**
- Vulnerable DOM or Document Object Model, which is the HTML code of the web application shown in request response.

**Point of Entry**
- The homepage stores *Last viewed product* in memory. Product page link is stored as a cookie in GET request for homepage.

**Mechanism of Exploit** 
- The URL of product page mentioned in payload is stored as `lastViewedProduct` cookie. 
- Alongside the link to product, malicious JavaScript is also stored as part of the cookie. It can be said that the cookie has been poisoned. 
- On loading the homepage, the exploit triggering is ensured by the `onload` event handler.

**Template**
`<iframe src="https://YOUR-LAB-ID.web-security-academy.net/product?productId=1&'><script>print()</script>" onload="if(!window.x)this.src='https://YOUR-LAB-ID.web-security-academy.net';window.x=1;">`
`


