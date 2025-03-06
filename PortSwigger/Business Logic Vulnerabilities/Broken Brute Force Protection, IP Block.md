*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Brute force the victim password.

**Point of Entry**
POST /login request. 

**Barrier to Entry**
- Three incorrect login attempts in a row result in IP address being blocked temporarily. 
- Brute forcing multiple candidate passwords will block attacker IP address.

**Bypassing Barrier to Entry**
- Designing an exploit that avoids IP block.
- The web application resets the counting for incorrect login attempts upon successful login attempt.
- Therefore, the attack should include intermittent successful logins between instances of brute forcing.

**Execution**
- Send POST/login request to Burp Intruder and select Pitchfork attack, where the username and password values are payload positions.
- For payload 1, use usernames *wiener* and *carlos* repeated one hundred times each in the mentioned order. 
- Username *wiener* has known password *peter*. These intermittent correct login details will bypass the barrier to entry. 
- For payload 2, copy and paste candidate password [list](https://portswigger.net/web-security/authentication/auth-lab-passwords) into notepad. Add peter as first candidate password in the list. Ensure that peter is in the list before every single candidate password.
- Sort attack instances by error response. A 302 response indicates password match. 
- Find the attack instance with a 302 response for username *carlos*, which shows the corresponding password.

