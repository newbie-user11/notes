*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Calling alert function without user interaction.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- GET search request

**Barrier to entry** 
- Single and double quotes, angle brackets, backslashes, and backticks are escaped. 
- Meaning these are encoded in browser request, which blocks exploits making their use.

**Bypassing Barrier to Entry**
- Search term is reflected in a JavaScript tag. 
- A payload starting with `$` and placed between `{}` will be executed on reflection in response.

**Template Exploit**
`${alert(1)}`
