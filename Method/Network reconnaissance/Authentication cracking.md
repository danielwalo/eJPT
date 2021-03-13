# Authentication cracking

## Hydra
For network attacks.

`hydra -L <USER_FILE> -P <PASS_FILE> <SERVICE>://<IP> -t <THREADS>`

## John the Ripper
For downloaded hashes.

john <FILE_TO_CRACK> --wordlist=<PASS_FILE>

As a last resort, add the `-rules` option to mangle passwords.

## Some credential files to try

Use shorter lists for network attacks.

### Users

- `/usr/share/ncrack/minimal.usr`
- `usr/share/seclists/Usernames/top-usernames-shortlist.txt`

### Passwords

- `/usr/share/seclists/Passwords/Leaked-Databases/rockyou-10.txt`
- `/usr/share/seclists/Passwords/Leaked-Databases/rockyou-15.txt`
- `/usr/share/seclists/Passwords/Common-Credentials/top-passwords-shortlist.txt`
- `/usr/share/seclists/Passwords/Common-Credentials/10k-most-common.txt`
- `/usr/share/wordlists/rockyou.txt.gz` (unpack first)