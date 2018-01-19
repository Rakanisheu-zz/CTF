Things to check before you start:

Read the CTF instructions a few times. Often there will be hidden clues as well as some red herrings to throw you off. Questions to ask yourself

- What are they looking for you to find
- What is the setup required (DHCP)
- Are they telling you what the setup is (mail server, web host, terminal server)

Lets run through the start process

1) Make sure the VM is setup correctly (ie it has an IP address)
2) What does the login screen show you? (username, IP address, OS build number etc)

** Onto Kali: **

Lets assume we dont know the IP address of the host we are trying to access (in real-life its not so easy as looking at the terminal).

nmap: (https://hackertarget.com/nmap-cheatsheet-a-quick-reference-guide/)

With nmap there are so many switches and ways to run about this. Lets start off with a quick scan

Scanning a range of IPs:

nmap 192.168.1.0/24  

Lets try a scan using UDP (instead of TCP SYN)

nmap -sU -p- 192.168.1.0/24  ( -p- scans all ports)

Assuming we got some hits for the above lets expand on them (see if we can find some OS details)

nmap -A 192.168.1.0/24  ( -A OS and services)

You can run multiple nmap scans and you may want to output them to a file for later review (so you dont have to re-run, some scans can take a while)

nmap -A 192.168.1.0/24 -oX output.xml (outputs to an xml file)
