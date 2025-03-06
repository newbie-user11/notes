*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Trick user into visiting exploit server.

**DOM**
- Vulnerable DOM or Document Object Model, which is the HTML code of the web application shown in request response.

**Point of Entry**
- Visit to any blogpost returns response containing ``<a href='#' onclick='returnURL' = /url=https?:\/\/.+)/.exec(location); if(returnUrl)location.href = returnUrl[1];else location.href = "/"'>Back to Blog</a>``
- This DOM code is for the *home* button that returns user to blog homepage, which is our point of entry.

**Mechanism of Exploit** 
- When placed in URL bar, user is redirected to the URL mentioned in the payload, which is the URL of the exploit server.

**Template**
`https://YOUR-LAB-ID.web-security-academy.net/post?postId=4&url=https://YOUR-EXPLOIT-SERVER-ID.exploit-server.net/`
`


