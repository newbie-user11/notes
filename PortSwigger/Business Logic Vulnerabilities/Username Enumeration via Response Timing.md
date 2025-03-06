*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Enumerate a valid username and brute force the password.

**Point of Entry**
POST /login request. 

**Barrier to Entry**
IP-based brute force protection.

**Bypassing Barrier to Entry**
Add *X-Forwarded-For* header to POST /login request to spoof IP address.

**Execution**
- Send POST/login request to Burp Intruder and select Pitchfork attack. 
- Highlight the space after *X-Forwarded-For* header and username value as payload positions.
- For payload 1, set numbers as payload type. For payload 2, copy candidate username [list](https://portswigger.net/web-security/authentication/auth-lab-usernames) and add as payload. 
- Start attack and wait till finish. Sort attack instances by *Response received* and *Response completed*. 
- The instance with the longest response time contains a username match. Copy it, return to *Positions* tab and replace username value.
- Remove username value as payload position, and instead highlight password as payload position. 
- For payload 2, copy candidate password [list](https://portswigger.net/web-security/authentication/auth-lab-passwords) to replace the username list as payload and start attack.
- Sort attack instances by error response. A 302 response indicates password match.
- Use the username and password combination to login.

