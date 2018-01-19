#### Introduction

nmap is network security scanner that we can use to map the network. In the cases in CTF's where we dont know the target IP address we will have 
to go scanning the network. 

#### Source

nmap is built into Kali but the source is: 

- https://nmap.org/

#### Using nmap

With nmap there are so many switches and ways to run about this. Lets start off with a quick scan

Scanning a range of IPs:

* nmap 192.168.1.0/24 *

Lets try a scan using UDP (instead of TCP SYN)

* nmap -sU -p- 192.168.1.0/24  ( -p- scans all ports) *

Assuming we got some hits for the above lets expand on them (see if we can find some OS details)

* nmap -A 192.168.1.0/24  ( -A OS and services) *

You can run multiple nmap scans and you may want to output them to a file for later review (so you dont have to re-run, some scans can take a while)

* nmap -A 192.168.1.0/24 -oX output.xml (outputs to an xml file) *

::: SYN scan Default Ports

* nmap -nvv --max-retries=1 -T4 -oA xxx.xxx.xxx_%T_%D -sS -O xxx.xxx.xxx.xxx

::: SYN scan All Ports

* nmap -nvv --max-retries=1 -T4 -oA xxx.xxx.xxx_%T_%D -sS -O -p- xxx.xxx.xxx.xxx

Take the list of open ports, e.g.: 21,22,80,443,139 and scan them with Nmap's Scripting Engine (NSE)

::: Services Scan scan

* nmap -nvv --max-retries=1 -T4 -oA xxx.xxx.xxx_%T_%D -A -p 21,22,80,443,139 --script-timeout=5m xxx.xxx.xxx.xxx

::: INTENSE Services Scan scan

* nmap -nvv --max-retries=1 -T4 -oA xxx.xxx.xxx_%T_%D -A -p 21,22,80,443,139 --script=all --script-args=unsafe=1 xxx.xxx.xxx.xxx

::: UDP scan

* nmap -nvv --max-retries=1 -T4 -oA xxx.xxx.xxx_UDP_%T_%D -sU xxx.xxx.xxx.xxx
