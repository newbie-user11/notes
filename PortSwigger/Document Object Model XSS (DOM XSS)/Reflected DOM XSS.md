*This information is only for the purposes of education and skills development.*

**XSS**
- In Cross Site Scripting or *code injection*, malicious JavaScript payload is injected across different code sites within the same website. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- Response to search request indicates vulnerability in DOM or Document Object Model.
- In the reflected response, see how search term is parsed in JSON format code. This is our point of entry.

**Barrier to entry** 
- To accept search terms including quotation marks, `"` is changed to `\"`, which is called escaping quotation mark.
- Due to this, single `"` followed by payload does not work. 

**Bypassing Barrier to Entry**
- Start payload with `\"`, which will result in `"\\"`. 
- This highlights that the search term is `\\`, and has ended. 
- JavaScript following the `"\\"` is executed, allowing our payload entry. 

**Template Payload**
`\"-alert(1)}//`


