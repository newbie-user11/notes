*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Brute force username and password

**Point of Entry**
POST /login request. 

**Execution**
- Send POST/login request to Burp Intruder and highlight the username value as payload position. 
- Copy candidate username [list](https://portswigger.net/web-security/authentication/auth-lab-usernames) and add as payload.
- Go to *Settings* tab and click add under Grep - Extract. Find and highlight *Invalid username or password*. Click OK.
- Start attack and sort the error message column to find the one odd message. This attack instance contains a username match.
- Copy the username and return to *Positions* tab. Replace username value and highlight password as payload position. 
- Copy candidate password [list](https://portswigger.net/web-security/authentication/auth-lab-passwords). Replace payload list and start attack.
- Sort attack instances by error response. A 302 response indicates password match.
- Use the username and password combination to login.

