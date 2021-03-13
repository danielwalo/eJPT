# Host discovery

You'll need to guess the host role in order to do ARP poisoning.

## fping

`fping -a -g <IP_RANGE> 2>/dev/null`

## Nmap

`nmap -sn <IP_RANGE>`

## Table example

| Host | Operating system | Confidence | Role |
|-|-|-|-|
| 10.0.0.1 | pfSense 2.6.0| 95 % | Router |
| 10.0.0.10 | Windows 10 Home 1809 | 95 % | Client |
| 10.0.0.11 | Ubuntu 16.04 | 90 % | MySQL server |