# Service fingerprinting

Start with an nmap scan. Update versions as you explore services and Nessus reports.

## Nmap

`nmap -sV <IP>`

## Table example

| Port | Protocool | State | Service | Version |
|-|-|-|-|-|
| 22 | tcp | open | OpenSSH | 8.5p1 | 
| 80 | tcp | open | Apache HTTP Server | 2.4.46 |
| 8080 | tcp | open | Apache Tomcat | 8.5.64 |