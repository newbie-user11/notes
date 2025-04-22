Simply assuming a webpage exists, then confirming whether it does or does not. 
To confirm whether a webpage exists, a potentially existing webpage is requested. If it exists, the webpage opens with a 200 OK response. If it does not exist, a not found 404 response is returned.

It is common to fuzz for a list of potentially existing webpages. Such a list is entered into a wordlist text file.

**FUZZ assigns point to append words from wordlist. Do not remove when replacing capitalised command parts with target and port number, and other parts of path**

*Webpage extention fuzzing*:
`ffuf -w /home/kali/Desktop/web-extensions.txt:FUZZ -u http://SERVER_IP:PORT/DIRECTORYFUZZ`

Once extension has been found perform webpage fuzzing.
*Webpage fuzzing*:
`ffuf -w /home/kali/Desktop/directory-list-2.3-small.txt.txt:FUZZ -u http://SERVER_IP:PORT/DIRECTORY/FUZZ.EXTENSION`

For fuzzing files at the set path and set levels above and below the path through *recursive fuzzing*:
`ffuf -w /home/kali/Desktop/directory-list-2.3-small.txt:FUZZ -u http://SERVER_IP:PORT/FUZZ -recursion -recursion-depth 1 -e .EXTENSION -v`

*Subdomain fuzzing* at vhost `.academy.htb`:
`ffuf -w /home/kali/Desktop/subdomains-top1million-5000.txt:FUZZ -u http://94.237.53.146:54699/ -H 'Host: FUZZ.academy.htb' -t 100 -fs 986`
`
*Parameter fuzzing GET*:
`ffuf -w /home/kali/Desktop/directory-list-2.3-small.txt -H 'Host: admin.academy.htb' -u http://94.237.57.153:33965/admin/admin.php?FUZZ=key -t 100 -v -fs ***` 

*Parameter fuzzing POST*:
`ffuf -w /home/kali/Desktop/directory-list-2.3-small.txt -H 'Host: admin.academy.htb' -u http://94.237.57.153:33965/admin/admin.php -X POST -d 'FUZZ=key' -H 'Content-Type: application/x-www-form-urlencoded' -fs 798`

Curl on POST output:
`curl http://94.237.57.153:33965/admin/admin.php -X POST -d 'id=key' -H 'Host:admin.academy.htb' 'Content-Type: application/x-www-form-urlencoded'`

Curl on Username:
`ffuf -w /usr/share/wordlists/seclists/Usernames/xato-net-10-million-usernames.txt:FUZZ -u http://faculty.academy.htb:{PORT}/../page.ext -X POST -d 'username=FUZZ' -H 'Content-Type: application/x-www-form-urlencoded'` -fs 781