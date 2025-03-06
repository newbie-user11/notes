*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Brute force the victim's password to access their account page.

**Point of Entry**
POST /login request. 

**Execution**
- Submit an invalid username and password combination to generate a POST /login request. Send this request to Burp Intruder.
- Select attack type as *Cluster Bomb*. Set payload position 1 at username value, and payload position 2 after the password value.
- Copy candidate username [list](https://portswigger.net/web-security/authentication/auth-lab-usernames) and insert as payload 1. For payload 2, generate 5 null payloads. Start attack.
- Find the attack instance that contains an error message in response *You have made too many incorrect login attempts.* 
- Send this instance to Intruder and open it. Select *Sniper* attack type, then copy and paste password [list](https://portswigger.net/web-security/authentication/auth-lab-passwords) into payload. Under settings, select the error message received earlier under Grep-Extract. 
- Start attack and wait to finish. The attack instance with the odd error message indicates password match. Use this password to login. 

