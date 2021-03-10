# Checklist

## Information gathering

- [ ] Read instructions carefully.
- [ ] Understood goals.
- [ ] Noted keywords, e.g. company name.

## Network reconnaissance

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
Did the following on all web services.

- [ ] Fingerprinted web server.
- [ ] Fingerprinted web framework and version.
- [ ] Tested default credentials.
- [ ] Crawled with Burp Suite.
- [ ] Fuzzed files and directories. [[Directory discovery]]
- [ ] Manually browsed the web application.
	- [ ] Noted pages with GET parameters for SQLi test.
	- [ ] Noted names and e-mail addresses.
- [ ] Checked for unusual headers.
- [ ] Checked all pages for comments.
- [ ] Checked all input methods for [[Cross-Site Scripting]]
- [ ] Checked all input methods for [[SQL injection]]
	- [ ] Query parameteres
	- [ ] Forms