*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Retrieve contents of  `/etc/passwd`.

**Path Traversal**
Using the path of a directory or a file to access it by specifying it at a point of entry.

**Point of Entry**
Product image GET request filename parameter can be edited.

**Execution**
- Start intercept and open any product on ecommerce site. This issues a product image GET request alongside other requests.
- Replace filename parameter value with `/etc/passwd`.
- Add `../` to move down a directory as the file may be stored further folders down.

**Template Payload**
`../../../etc/passwd`


