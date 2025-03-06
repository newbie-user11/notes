Also referred to as reconnaissance. For web application testing, the goal of web reconnaissance is identification of points of entry at the target.
These points of entry must be realistically exploitable. 
Information gathering, or reconnaissance, may be *active* or *passive*.
# Active Reconnaissance
This method involves direct interaction with the web application utilising following methods.
- Scanning for open ports at the target IP address using Nmap.
- Probing for known vulnerabilities of the application being tested, for which *Common Vulnerabilities and Exposures* databases may be referred to. As well as commonly found vulnerabilities. For instance, SQLi or XSS using Nessus.
- *Network mapping* using traceroute to trace the path of packets of information travelling through a network.
- *Banner Grabbing* by connecting to a port and examining its HTTP banner to identify its server software and version.
- Using nmap -O to determine target OS server. This method is called OS Fingerprinting.
- *Service Enumeration* using `nmap -sV` to determine web server running in background. 
- *Web Spidering* to crawl the target website for mapping out the website as a directory structure with identified web pages, directories, and files.
- *Active subdomain enumeration* to identify old and/or forgotten subdomains of the target web application. These parts are usually webpage prototypes, hidden login portals, *legacy* or outdated webpages, or files containing sensitive information. Two commonly used methods exist.
	1) DNS Zone Transfer using `dig @<nameserver> ANY <domain> axfr`. This command will extract a complete list of subdomains at the target web application, but only if server is misconfigured.
	2) [[Subdomain Brute Force Enumeration]] to test whether a list of potential subdomain names matches technique tools 
Active Reconnaissance involves direct interaction with target, which may trigger alerts/alarms. To avoid triggering alerts, *passive reconnaissance* techniques may be utilised.
# Passive Reconnaissance
This method involves information gathering about target by analysing publicly available information.
- Search engines queries about target. Google, duckduckgo, shodan, etc for news, general information, social media activity, etc.
- WHOIS Lookup to find publicly available registration information regarding target domain. Could reveal email addresses and phone numbers of individuals responsible for managing the domain.
	- WhoIsFreaks can reveal changes in ownership.
- DNS records to identify target subdomains, mail servers, other infrastructure.
- *Web archive analysis* through *Wayback Machine* to view past versions of target website. This may reveal hidden information, or vulnerabilities.
- Social media analysis by searching for current or ex-employees of an organisation as potential social engineering targets.
- Code repositories such as GitHub for exposed credentials or vulnerabilities.
- *Passive subdomain emuneration* to discover subdomains of the web application using publicly accessible information.
	- Certificate Transparency logs and public repositories of SSL/TLS certificates. Subdomains are found in *Subject Alternative Name* field.
	- Search engine operator `site:<insert target domain>` on Google or DuckDuckGo.
	- Online DNS databases that could be accessed through Google.