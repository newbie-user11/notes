*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Using GraphQL introspection, delete username Carlos.

**GraphQL**
- It is an API query language for communication between the client and server. 
- Efficiency is its main feature, enabling users to request and receive the exact information required.

**Point of Entry**
GET /api request that shows user details. 

**Barrier to Entry**
The point of entry has protection against introspection, which is verified by browsing to location /api in the URL bar.

**Bypassing Barrier to Entry**
- A *Query not present* error is returned by browsing to /api, indicating that this endpoint accepts queries. 
- If an introspection GraphQL is included as URL in GET request, it will be accepted. 

**Execution**
- Send the GET request to repeater and add Introspection query.
- See error in response, after `____schema` add `%0a` which stands for newline character `\n`.
- Under Target, in sitemap find GraphQL request containing `getUser` in request body and send it to repeater. 
- This request contains `id` parameter which refers to user id. Send this request to Repeater. 
- Change the default value of `id` from zero to another number to find the value that denotes Carlos's id. 
- Return to sitemap and find GraphQL request to delete user. Send it to repeater and replace the default id value to Carlos's id. Send request to delete username Carlos.