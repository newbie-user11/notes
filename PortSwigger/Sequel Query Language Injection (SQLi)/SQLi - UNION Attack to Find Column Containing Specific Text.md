**Objective**
Locate a column with specific text using SQLi UNION attack.

**SQLi**
- Structured Query Language or SQL injection occurs when attacker sends malicious input to SQL database. 
- Lack of validation or sanitisation of input leaves the database vulnerable to exploitation of stored information.
- Refer [SQL Cheatsheet](https://portswigger.net/web-security/sql-injection/cheat-sheet).

**Point of Entry**
- The category filter function is vulnerable to SQLi. 
- Replace category filter value in GET request with SQL based payload `'+UNION+SELECT+NULL+NULL+NULL--`
- Each NULL represents column with text or *string* being searched.

 **Barrier to Entry**
- Column containing string `'w1Sqbj'` is unknown.
- Replacing wrong `NULL` with the string value returns error.

**Bypassing Barrier to Entry**
- Hit and trial by replacing `NULL` with `'w1Sqbj'` to locate column containing the string.