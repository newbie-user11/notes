*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Target:** User email account.

**Request being forged:** Email change request

**Cross Site because:** Forged request for unintended email change comes from exploit server, not the blogsite.

**Point of Entry**
- Search function is the point of entry for our exploit. *SameSite=None* reflected in blog search response indicates vulnerability due to lack of same site cookie restrictions.

**Barrier to Entry**
Tampering with session cookie results in logout.

**Bypassing Barrier to Entry** 
- Upon login, a CSRFKey cookie is assigned alongside session cookie, but they are not linked. 
- A request goes through as long as there is a set of matching CSRFKey cookie and CSRF token, even if these values are from a different user's account.

**Exploit**
- Using BurpSuite engagement tools, the exploit is made from an email change request with its own CSRFKey cookie and CSRF token.
- For relevant action of user search to trigger unintended email address change, the `<script>` tag in the exploit is swapped with the `<img src>` template below.


**Template**
`<img src="https://YOUR-LAB-ID.web-security-academy.net/?search=test%0d%0aSet-Cookie:%20csrfKey=YOUR-KEY%3b%20SameSite=None" onerror="document.forms[0].submit()">`