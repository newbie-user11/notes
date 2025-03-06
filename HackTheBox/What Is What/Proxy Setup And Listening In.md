When a user accesses information on the internet, HTTP requests are sent between their web browser and server.
These HTTP requests contain sensitive information that can be viewed by an attacker. 

# Set Up Proxy
- To view the sensitive information, HTTP request traffic is routed through a proxy, which is a combination of an IP address and a port number.
- An example of a proxy address is 127.0.0.1:8080, where 127.0.0.1 is an IP address and 8080 is a port number, which are separated by a colon `:`.
- Proxychains is a tool utilised for proxy that is set up via a linux terminal. Set up proxychains by following these [instructions](https://academy.hackthebox.com/module/110/section/1053).
- Consequently, Burp Suite can be used to read HTTP requests routed through the proxy, which is called listening in.
- To add the proxy in Burp Suite, under the *Proxy* menu select *Proxy settings*, and find Proxy listeners section. In that section, click the *Add* button then enter the proxy address.

# Confirm Proxy Working
- Run the first then the second nmap scan.
	1. ```nmap -h | grep -i prox```
	2. ```nmap --proxies http://127.0.0.1:8080 SERVER_IP -pPORT -Pn -sC```
- If the nmap scan request can be viewed in Burp Suite, the proxy set up was successful.