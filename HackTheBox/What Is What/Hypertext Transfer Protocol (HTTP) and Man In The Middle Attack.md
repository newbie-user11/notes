- What is hypertext? Links that can be clicked to access information.
- If HTTP is used to visit a website that enforces access through HTTP Secure (HTTPS), request to display website is redirected from port 80 to port 443. 
	- Why is this important? Connection via port 80 is unencrypted, but port 443 is encrypted.
	- Unencrypted communication via port 80 is in plain text. Usernames and passwords are readable. Encrypted communication via port 443 is coded, thus not readable.
	- If communication traffic can be forced from port 443 to port 80, information becomes plain text. 
	- This type of information interception is called Man in the Middle attack. There are protections against such attacks.