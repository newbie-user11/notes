*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Target:** User email account.

**Request being forged:** Email change request

**Cross Site because:** Forged request for unintended email change comes from exploit server, not the blogsite.

**Point of Entry**
- Referrer header in POST request for email change is vulnerable, because the database relies on referrer web address being a valid match. 
- Referrer header's absence does not affect the request validity, making its absence our point of entry.

**Barrier to entry** 
- Creating an exploit that forges the removal of the referrer header.

**Bypassing barrier to entry**
Using `<meta>` tag in the exploit's html header to suppress referrer header. 

**Template**
 `<meta name="referrer" content="no-referrer">`