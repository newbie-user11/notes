*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Sign in as admin to delete username Carlos.

**GraphQL**
- It is an API query language for communication between the client and server. 
- Efficiency is its main feature, enabling users to request and receive the exact information required.

**Point of Entry**
POST GraphQL request to reveal admin login details for login.

**Execution**
- Login as Wiener. Right click the login request and select GraphQL option to set introspection query. Send request.
- Save the received response to Site Map using the same right click option.
- Find GraphQL request containing `getUser` in body and send to repeater. This request contains `id` parameter which refers to user id.
- Send this request to Repeater. Change the default value of `id` from zero to another number to find the value that denotes admin id. 
- Retrieve admin user login details to login.