*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Retrieve contents of  `/etc/passwd`.

**Path Traversal**
Using the path of a directory or a file to access it by specifying it at a point of entry.

**Point of Entry**
Product image GET request filename parameter can be edited.

**Barrier to Entry**
- There is protection against path traversal sequences. 
- There is an additional layer of protection in the form of accepting only URL encoded input. 
- This input is decoded in backend.

**Bypassing Barrier to Entry**
URL encoding our payload.

**Execution**
- Start intercept and open any product on ecommerce site. This issues a product image GET request alongside other requests.
- In the product image GET request, replace filename parameter value with template payload file path to reveal file contents.

**Template Payload**
`..%252f..%252f..%252fetc/passwd`


