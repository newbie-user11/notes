**Objective**
Determine number of columns returned by SQLi UNION attack.

**SQLi**
- Structured Query Language or SQL injection occurs when attacker sends malicious input to SQL database. 
- Lack of validation or sanitisation of input leaves the database vulnerable to exploitation of stored information.
- Refer [SQL Cheatsheet](https://portswigger.net/web-security/sql-injection/cheat-sheet).

**Point of Entry**
- The category filter function is vulnerable to SQLi. 
- Replace category filter value in GET request with SQL based payload `'+UNION+SELECT+NULL--`

 **Barrier to Entry**
- Attacking point of entry with payload returns error.

**Bypassing Barrier to Entry**
- Attack again with an additional `+NULL`.
- Add additional `+NULL` to the payload with each repeated attempt attack until successful.
