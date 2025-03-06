*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Access administrator interface and delete user named *Carlos*.

**SSRF**
- In Server Side Request Forgery the attacker forges a request that results in the server unintendedly making an unauthorised request.

**Point of Entry**
- The admin panel is at `http://localhost/admin`. Access without login is blocked.
- On any product page, use *Check Stock* function and see that its POST request contains `stockApi` header.  This is our point of entry. 

**Barrier to Entry**
- Change the value of `stockApi` header to `http://127.1/admin`. Request is blocked.

**Bypassing Barrier to Entry** 
- In payload `http://127.1/admin`, replace `a` in admin with its double encoded form `%2561`.
- Update payload with payload to delete Carlos's account.

**Template**
`http://127.1/%2561dmin/delete?username=USERNAME`


