# Checklist

## Information gathering

- [ ] Read instructions carefully.
- [ ] Understood goals.
- [ ] Noted keywords, e.g. company name.

## Network reconnaissance

- [ ] Ran [AutoRecon](https://github.com/Tib3rius/AutoRecon).
- [ ] Created host table. [[Host discovery]]
- [ ] Added OS and versions. [[OS fingerprinting]]
- [ ] Created service table for all hosts. [[Service fingerprinting]]

## Vulnerability assessment

- [ ] Ran Nessus basic network scan on all hosts.
- [ ] Ran Nessus web application scan on hosts with http(s) services.
- [ ] Added vulnerabilities that should be investigated to [[Vulnerability report]].
- [ ] Updated host and service tables with new information.

## Web applications
Did the following cycle on all web services until done.

- [ ] Fingerprinted web server.
- [ ] Fingerprinted web framework and version. [[Web framework fingerprinting]]
	- [ ] Tested default credentials.
- [ ] Ran [Nikto](https://github.com/sullo/nikto) on all frameworks.
- [ ] Manually browsed the web application.
	- [ ] Tested inputs.
	- [ ] Noted interesting information, e.g. names and e-mail addresses.
- [ ] Used [OWASP Zed Attack Proxy](https://www.google.com/search?client=firefox-b-e&q=github+owasp+zap):
	- [ ] Excluded requests from ZAP if they generate unwanted data.
	- [ ] Spidered application.
	- [ ] Tried [[Directory discovery]].
	- [ ] Ran Active Scans.
- [ ] Gathered information.
	- [ ] Reviewed Information Disclosure alerts in ZAP.
	- [ ] Reviewed unusubal headers.
	- [ ] Reviewed HTML comments.
		- [ ] Didn't stop at `</html>`.
- [ ] Checked all input methods for [[Cross-Site Scripting]]
- [ ] Checked all input methods for [[SQL injection]]
- [ ] If found domains, added to `etc/hosts` and framework table.
- [ ] Tried all known username- and password combinations on restricted areas.
- [ ] If missing credentials, noted restricted area for [[Authentication cracking]]

## Network attacks

- [ ] Checked for [[Null sessions]]
- [ ] Checked [[ARP poisoning]] opportunities.
- [ ] Checked [[Blind remote code execution]] on ZAP server-side execution alerts.
- [ ] Tried all exploits from [[Vulnerability report]].
- [ ] Tried all known username- and password combinations against all services.
- [ ] If all else failed, ran dictionary attack on services. [[Authentication cracking]]

## System attacks

- [ ] When gaining [[Shell]] access:
	- [ ] tried UAC bypass if necessary
	- [ ] reviewed network configuration
		- [ ] [[Routes]]
		- [ ] hosts
	- [ ] searched for interesting files
	- [ ] reviewed information about users
	- [ ] reviewed installed applications
	- [ ] dumped hashes for [[Authentication cracking]] if possible
- [ ] Tried to crack password hashes.