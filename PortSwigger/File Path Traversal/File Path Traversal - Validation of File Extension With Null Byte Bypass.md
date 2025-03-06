*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Retrieve contents of  `/etc/passwd`.

**Path Traversal**
Using the path of a directory or a file to access it by specifying it at a point of entry.

**Point of Entry**
Product image GET request filename parameter can be edited.

**Barriers to Entry**
There is protection against file path traversal sequences. 
- The web application validates the file extension to verify that the file named in the request is an image.
- Additionally, `/etc/passwd` is not an image file as it does not end with an extension such `.svg` or `.png`.

**Bypassing Barrier to Entry**
- Add `.png` extension to the `/etc/password` file to bypass file type validation in the GET request to gain entry.
- Use null byte `%00` to get the server to ignore anything following the null byte, which is the `.png` extension.

**Execution**
- Start intercept and open any product on ecommerce site. This issues a product image GET request alongside other requests.
- In the product image GET request, replace filename parameter value with template payload file path to reveal file contents.

**Template Payload**
`../../../etc/passwd%00.png`


