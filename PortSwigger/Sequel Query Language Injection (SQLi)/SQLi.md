*Remember! Do not attempt to use this information outside PortSwigger Academy Labs. It is only for the purposes of education and skills development.*

`'+OR+1=1--`
' breaks pre existing query 
+is for encoding into URL readable format
OR is used instead of AND to ensure a true response
1=1 is a true expression which is needed for a confirmed true response

`administrator'--` when entered in username field
it has the following outcome:
```
SELECT * FROM users WHERE username = 'administrator'--' AND password = '<password>'
```
-- marks what follows the code as a comment, meaning that code after --, which is ' AND password = '<password>' is ignored by the database executing the command. Effectively, bypassing password check.