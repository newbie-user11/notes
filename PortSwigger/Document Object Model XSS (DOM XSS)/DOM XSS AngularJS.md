*This information is only for the purposes of education and skills development.*

**XSS**
- In Cross Site Scripting, malicious JavaScript payload is injected across different sites within the same website. 
- OWASP suggests calling it *code injection* for simplicity.
- As the attack occurs in the user's browser session, it is client side instead of server side.

**Point of Entry**
- Vulnerable DOM or Document Object Model, which is the HTML code of the web application shown in request response.
- For a search request, `<body ng-app>` tag in response body of the page indicates that it is based on the outdated, thus vulnerable, AngularJS framework. 

**Payload**
The presence of `<body ng-app>`, called AngularJS directive enables execution of JavaScript within double curly brackets.

**Template**
`{{$on.constructor('alert(1)')()}}`


