# DNS Resolution Issue in Kali Linux

## Problem
Unable to access websites. Firefox was not working.
Ping to google.com failed with "Temporary failure in name resolution".

## Investigation
Ping to 8.8.8.8 worked, which means internet connection was fine.
So the issue was related to DNS.

## Fix
Configured DNS manually using NetworkManager:

nmcli connection modify "Airtel_NT2" ipv4.dns "8.8.8.8 1.1.1.1"
nmcli connection modify "Airtel_NT2" ipv4.ignore-auto-dns yes
nmcli connection down "Airtel_NT2"
nmcli connection up "Airtel_NT2"

## Commands Used
- ping google.com
- ping 8.8.8.8
- nmcli

## Learning
- Difference between internet connectivity and DNS
- How DNS resolves domain names to IP addresses
- How to troubleshoot network issues in Linux
