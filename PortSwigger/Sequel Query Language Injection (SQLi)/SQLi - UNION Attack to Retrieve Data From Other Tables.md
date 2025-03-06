**Objective**
Retrieve administrator's username and password using SQLi UNION attack.

**SQLi**
- Structured Query Language or SQL injection occurs when attacker sends malicious input to SQL database. 
- Lack of validation or sanitisation of input leaves the database vulnerable to exploitation of stored information.
- Refer [SQL Cheatsheet](https://portswigger.net/web-security/sql-injection/cheat-sheet).

**Point of Entry**
- The category filter function is vulnerable to SQLi. 
- Intercept and choose a filter.
- Replace category filter value in GET request with SQL based payload `'+UNION+SELECT+'abc'+'def'--`
- Database content can be accessed and printed on ecommerce site.
- Login details of users are stored on table called `users` with columns named `username` and `password`.
  
 **Exploit to Entry**
- To reveal target details use payload `'+UNION+SELECT+username,+password+FROM+users--`
