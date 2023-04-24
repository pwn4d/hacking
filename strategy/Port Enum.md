# Basic Nmap Scan

##  `nmap -A -sV -vv -oN nmap-scan <ip>`

- -A : OS detection, version detection, script scanning, and traceroute
- -sV : Version Detection
- -vv: verbose
- (optional) -oN : output results to file



# Medium Nmap Scan (All Ports)

## `nmap -A -sV -p- -oN nmap-scan<ip>`

- -p- : Scans all 65535 ports


# Advanced Scan (UDP and TCP)

## `sudo nmap -sC -sV -p- -sU -oN nmap-scan <ip>`


- -sU : Scans all udp ports (this takes a while so maybe run on the side)
- sudo : root privileges are required to send UDP packets


