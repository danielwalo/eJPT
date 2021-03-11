# Checklist

## Information gathering

- [ ] Read instructions carefully.
- [ ] Understood goals.
- [ ] Noted keywords, e.g. company name.

## Network reconnaissance

- [ ] Ran autorecon.
- [ ] Created host table. [[Host discovery]]
- [ ] Added OS and versions. [[OS fingerprinting]]
- [ ] Created port table for all hosts. [[Port scanning]]
- [ ] Added services and versions. [[Service fingerprinting]]

## Vulnerability assessment

- [ ] Ran Nessus basic network scan on all hosts.
- [ ] Ran Nessus web application scan on hosts with http(s) services.
- [ ] Listed reportable vulnerabilities with CVSS and remediation.
- [ ] Update host and service tables with new information.

## Web applications
Did the following cycle on all web services until done.

- [ ] Ran Nikto.
- [ ] Fingerprinted web server.
- [ ] Fingerprinted web framework and version.
	- [ ] Tested default credentials.
- [ ] Manually browsed the web application.
	- [ ] Tested inputs.
	- [ ] Noted names and e-mail addresses.
	- [ ] Excluded requests from ZAP if they generate unwanted data.
- [ ] Spidered with ZAP.
- [ ] Fuzzed hidden files and directories in ZAP. [[Directory discovery]]
- [ ] Attacked with ZAP.
- [ ] Gathered information.
	- [ ] Reviewed Information Disclosure alerts in ZAP.
	- [ ] Reviewed unusubal headers.
	- [ ] Reviewed HTML comments.
		- [ ] Didn't stop at `</html>`.
- [ ] Checked all input methods for [[Cross-Site Scripting]]
- [ ] Checked all input methods for [[SQL injection]]
- [ ] If found domains, added to `etc/hosts` and connected.
- [ ] If missing credentials, noted restricted area for [[Brute force]]