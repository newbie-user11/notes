*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Promote own account to become administrator by reusing a request to promote a different account.

**Point of Entry**
POST request issued for promoting user Carlos while logged in as admin.

**Execution**
- Login to administrator account using provided details and promote Carlos under admin panel.
- Send the POST request issued to Burp Repeater. 
- Open another user session in incognito mode and login as wiener. Copy the cookie from this session.
- Return to the POST request in Repeater, replace the session cookie of the request and send it. Response states *Unauthorised*.
- Change the request method to GET by right clicking request. Replace username from carlos to wiener.
