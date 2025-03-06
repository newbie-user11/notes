**Objective**
Modify serialised object in session cookie to access admin privileges for deleting user Carlos.

**Point of Entry**
GET /my-account request issued on login.

**Execution**
- Send the GET request to Repeater an select the session cookie for inspection in Inspector.
- Notice that session cookie is decoded using *URL*+*Base-64* methods. Update the following parameters:
	- Username length attribute to 13.
	- Username from *wiener* to *administrator*.
	- Data type attribute from *s* to *i*; i.e., string to integer. 
	- Change access token value to number 0.
- Apply changes and send request. Change path of request to /admin, which reveals admin panel access. 
- However, admin privileges do not remain if trying to navigate to admin panel or any other page.
- Change request path to `/admin/delete?username=carlos`. Send request to delete user *Carlos*.