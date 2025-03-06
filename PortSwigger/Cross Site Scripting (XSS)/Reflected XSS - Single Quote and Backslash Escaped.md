*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Calling alert function without user interaction.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- GET search request

**Barrier to entry** 
- Single quotes and backslashes are escaped. Meaning they are encoded by browser, which effectively blocks exploit.

**Bypassing Barrier to Entry**
- Using `</script>` at the start of payload signals end of script. 
- This breaks the JavaScript string. A script payload placed after the tag will be executed as a script.

**Template Exploit**
`</script><script>-alert(1)</script>`


