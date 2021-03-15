# Routes and pivoting

## Show route table

### Linux

`ip route`

## Windows

`route PRINT -4`

## Add new route on Linux

`ip route add net <NETWORK> via <GATEWAY> dev <INTERFACE>`

## Using Metasploit for routing

If you compromise a machine on a previously inaccessible network, you can use Metasploit to open a proxy server that gives you access.

### Autoroute

Once you've got a meterpreter session:

```
meterpreter > background
msf6 > use post/multi/manage/autoroute
msf6 > post(multi/manage/autoroute) > set subnet <YOUR_TARGET_SUBNET>
msf6 > post(multi/manage/autoroute) > set session <YOUR_METERPRETER_SESSION>
msf6 > post(multi/manage/autoroute) > run
```

Metasploit creates a routing table. Packets to `<YOUR_TARGET_SUBNET>` are routed through `<YOUR_METERPRETER_SESSION>`.

Any Metasploit-action taken against `<RHOSTS>` that fall within `<YOUR_TARGET_SUBNET>` will be routed automatically.

### Start a socks proxy server

To use the new route outside Metasploit, start a socks proxy server and route traffic through it.

```
msf6 > use auxiliary/server/socks_proxy
msf6 auxiliary(server/socks_proxy) > set srvhost 127.0.0.1
msf6 auxiliary(server/socks_proxy) > set srvport 9050
msf6 auxiliary(server/socks_proxy) > set version 4a
msf6 auxiliary(server/socks_proxy) > run
```

### Check proxychains settings

Make sure `/etc/proxychains4.conf` has this line:

`socks4  127.0.0.1 9050`

### Start accessing the new network.

Prefare your command with `proxychains -q` and any requests that fall within `<YOUR_TARGET_SUBNET>` will be routed through `<YOUR_METERPRETER_SESSION>`.

`proxychains -q nmap -sn <YOUR_TARGET_SUBNET>`

Host discovery over socks proxy is very slow, so consider uploading nmap to a compromised and scanning the network from there.