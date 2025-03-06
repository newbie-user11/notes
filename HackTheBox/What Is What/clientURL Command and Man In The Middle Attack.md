cURL command is used to receive information from server.
- cURL follows HTTPS standards for secure communication. Data is encrypted and decrypted automatically.
- If a web application does not have a valid Secure Socket Layers (SSL) certificate for encrypted communication between client and server, a warning is issued on using cURL, ending the command.
- To skip the SSL certificate check and initiate curl regardless, -k flag is utilised: 
		`curl -k https://domain...` 


