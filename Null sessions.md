# Null sessions
Retrieves information about a Windows machine without credentials.

## Port scan

`nmap -sS -p 135,139,445 <IP>`

## Veryify null session vulnerability

Look for `<20>` flag on share.

### nmblookup

`nmblookup -A <IP>`

### enum4linux

`enum4linux -n <IP>`

## List shares

### smbmap

`smbmap -H <IP>`

### Nmap

`nmap --script smb-enum-shares <IP>`

### smbclient

`smbclient -L //<IP> -N`

### enum4linux

`enum4linux -S 192.168.99.162`

### Metasploit

`use auxiliary/scanner/smb/smb_enumshares`

## List users

### Nmap

`nmap --script smb-enum-users <IP>`

### enum4linux

`enum4linux -U 192.168.99.162`

### Metasploit

`use auxiliary/scanner/smb/smb_enumusers`

## Brute force shares list

`enum4linux -s <SHARES_FILE> <IP>`

## Brute force passwords

`nmap --script smb-brute <IP>`