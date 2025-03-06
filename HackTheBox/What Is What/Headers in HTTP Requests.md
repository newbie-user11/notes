# General Headers
**Date** holds date and time of message origination.
**Connection** is commonly labelled as *close* or *keep-alive*. Close denotes termination of connection. Keep-alive denotes that connection is open for communication.

# Entity Headers
**Content-Type** Information resource being transferred through HTTP is labelled based on type.
	**charset field** denotes the standard of information encoding, often UTF-8.
**Media-Type** Similar to *content-type*. Information resource being transferred is labelled based on type.
**Boundary** Boundary is an alphanumeric line of text that separates different parts of a HTTP request. 例えば：`b4e4fbd93540`
**Content-Length** Indicates size of the request in bytes.
**Content-Encoding** Indicates method of compression of information being transferred over HTTP. Smaller message size facilitates quicker processing of HTTP request.

# Request Headers
**Host** Domain name or IP address that the HTTP request is sent to.
**User-Agent** Provides information regarding client, typically web browser, requesting resources.
**Referer** Denotes the information requesting address.
**Accept** Indicates which media types are supported by the client (web browser). A value of `*/*` means all media types are accepted.
**Cookie** An unique identifier assigned to a HTTP request session between client and server. 
**Authorization** An unique identifier for clients that is stored on the client-side.

# Response Headers
**Server** Details of the server that processed the HTTP request.
**Set-Cookie** Client identifier in the same format as *Cookie* header in request. 
**WWW-Authenticate** Type of authentication required by client to access requested resource. 

# Security Headers
**Content-Security-Policy** Restricts the web browser to accepting requests from only trusted domains.
**Strict-Transport-Security** Forces web browser to use encrypted HTTPS, not unencrypted HTTP.
**Referrer-Policy** Policy dictating which values contained in the *Referer* header of the HTTP request is revealed in the HTTP response. Used to avoid disclosing sensitive information.