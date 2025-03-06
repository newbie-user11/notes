*This information is only for the purposes of education and skills development.*

**Objective**
Tricking user into clicking *Click Me* button to trigger print function.

**XSS**
- In Cross Site Scripting or simply *code injection*, malicious JavaScript payload is injected into web application code. 
- As the attack targets the user's browser session, it is client side instead of server side.

**Point of Entry**
- Vulnerable DOM or Document Object Model, which is the HTML code of the web application. The *Submit Feedback* page is our point of entry.
- An *iframe* HTML tag can be used for covering page with a layer that has a *Click Me* button positioned over the Submit Feedback button.

**Barrier to entry** 
*Click Me* button position over page. 

**Bypassing Barrier to Entry**
Finding the right placement for the *Click Me* button through hit and trial.

**Template**
`<style> iframe { position:relative; width:$width_value; height: $height_value; opacity: $opacity; z-index: 2; } div { position:absolute; top:$top_value; left:$side_value; z-index: 1; } </style> <div>Test me</div> <iframe src="YOUR-LAB-ID.web-security-academy.net/feedback?name=<img src=1 onerror=print()>&email=hacker@attacker-website.com&subject=test&message=test"></iframe>`

