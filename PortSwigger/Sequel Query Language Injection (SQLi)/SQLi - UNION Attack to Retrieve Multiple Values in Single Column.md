**Objective**
Retrieve administrator's username and password in single column using SQLi UNION attack.

**SQLi**
- Structured Query Language or SQL injection occurs when attacker sends malicious input to SQL database. 
- Lack of validation or sanitisation of input leaves the database vulnerable to exploitation of stored information.
- Refer [SQL Cheatsheet](https://portswigger.net/web-security/sql-injection/cheat-sheet).

**Point of Entry**
- The category filter function is vulnerable to SQLi. 
- Intercept and choose a filter.
- Replace category filter value in GET request with SQL based payload `'+UNION+SELECT+'abc'--`
- Database content can be accessed and printed on ecommerce site.
  
 **Payload Template**
- To reveal target login details, use payload `'+UNION+SELECT+NULL,username||'~'||password+FROM+users--`
