*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Access admin panel and delete user named Carlos.

**Point of Entry**
- GET request issued when visiting URL `https://0a71008a0313722d80e9ad5d00c900b4.web-security-academy.net/admin`.
  
**Barrier to Entry**
The frontend system blocks external access to admin panel at `https://0a71008a0313722d80e9ad5d00c900b4.web-security-academy.net/admin`.

**Bypassing Barrier to Entry**
- The backend of the application supports `X-Original-URL` header, which can be used to bypass the protection. 
- Start intercept and reload admin panel URL. Send the GET request issued consequently to Repeater. 
- In repeater, add `X-Original-URL:` as header and set its value to `/invalid`. A *not found* response indicates that URL value is accepted by server but no match is found. 
- Inserting a payload under this header will enable bypassing barrier to entry.

**Execution**
Replace `X-Original-URL` value to `/admin` to gain access to admin panel. Change it to 
