#### Introduction

Hydra is a password cracking utility that is very useful for cracking various types of systems. It supports a large number of systems:

- Cisco AAA
- Cisco auth
- Cisco enable
- CVS
- FTP
- HTTP(S)-FORM-GET
- HTTP(S)-FORM-POST
- HTTP(S)-GET
- HTTP(S)-HEAD
- HTTP-Proxy
- ICQ
- IMAP
- IRC
- LDAP
- MS-SQL
- MySQL
- NNTP
- Oracle Listener
- Oracle SID
- PC-Anywhere
- PC-NFS
- POP3
- PostgreSQL
- RDP
- Rexec
- Rlogin
- Rsh
- SIP
- SMB(NT)
- SMTP
- SMTP Enum
- SNMP v1+v2+v3
- SOCKS5
- SSH (v1 and v2)
- SSHKEY
- Subversion
- Teamspeak (TS2)
- Telnet
- VMware-Auth
- VNC and XMPP

#### Links

Hydra is built into Kali

- https://tools.kali.org/password-attacks/hydra

#### Usage

Attempting to login into to a remote system (as root) using a set password list

- hydra -l root -P /usr/share/wordlists/metasploit/unix_passwords.txt -t 6 ssh://192.168.0.185

Attempting to login into to a remote system (as root) using a custom saved password list

- hydra -l root -P passwords.txt -t 6 ssh://192.168.0.185

Attempting to login into to a remote system using a custom login list and using a custom saved password list (note the upper case "L")

- hydra -L login.txt -P passwords.txt -t 6 ssh://192.168.0.185
