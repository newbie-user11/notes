**Objective**
Reveal SQL database version details.

**SQLi**
- Structured Query Language or SQL injection occurs when attacker sends malicious input to SQL database. 
- Lack of validation or sanitisation of input leaves the database vulnerable to exploitation of stored information.

**Point of Entry**
- Discover that the category filter function is vulnerable to SQLi. 
- By replacing category filter value in GET request with SQL `'+UNION+SELECT+'abc','def'+FROM+dual--`.
- Both `'abc'` and `'def'` are printed on the page. 
- This reveals category filter as point of entry for a similar query to print database details on page.
- Replace mentioned SQL with payload to reveal database details.

**Payload**
`'+UNION+SELECT+@@version,+NULL#`

