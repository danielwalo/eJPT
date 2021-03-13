# Directory discovery

Find hidden files or directories on a web application.

## OWASP Zed Attack Proxy

See: [Forced Browse](https://www.zaproxy.org/docs/desktop/addons/forced-browse/)

## gobuster

`gobuster dir -u <URL> -w <WORDLIST> -t <THREADS>`

Use `--proxy` to run through ZAP.

## Suggested extensions

- bak
- old
- xxx
- txt
- php
- html

## Suggested lists

- `/usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt`
- `/usr/share/seclists/Discovery/Web-Content/quickhits.txt`
- `/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt`