**Objective**
Modify serialised object in session cookie to delete `morale.txt` file located in user Carlos's home directory.

**Point of Entry**
POST /login request issued on login.

**Execution**
- Login to own account. Open Site Map and find request that includes `/libs/CustomTemplate.php`. Send this request to Repeater.
- The source code of this request can be read by appending a `~` to the filename and sending the request.
- Check that the source code contains `CustomTemplate` class that contains `__destruct()` magic method. 
- This will invoke the `unlink()` method on the `lock_file_path` attribute which will delete the file on this path.
- Send a POST request including a session cookie to Repeater. 
- Highlight the cookie and using Inspector, edit it to `O:14:"CustomTemplate":1:{s:14:"lock_file_path";s:23:"/home/carlos/morale.txt";}`.
- Apply changes and copy the cookie. Right click on webpage and *inspect element*. Find and open the cookie tab. 
- Replace the session cookie and reload page to execute the exploit.