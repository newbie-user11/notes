*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective:** Calling alert function without user interaction.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- URL for GET search request

**Barrier to entry** 
- HTML tags are blocked except SVG tags and events.

**Bypassing Barrier to Entry**
- Send GET search request to Burp Intruder, and replace search term with `<>`.
- Set payload between `<>`. For payload, refer [link](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)
- Attack returns a 200 success response for HTML tags - `svg`, `animatetransform`, `title`, and `image`. While, most other tags return a 400 error response.
- Reset search term as `<svg><animatetransform%20=1>` and attack with HTML events at payload position between 20 and =.

**Template Exploit**
`https://YOUR-LAB-ID.web-security-academy.net/?search=%22%3E%3Csvg%3E%3Canimatetransform%20onbegin=alert(1)%3E`

