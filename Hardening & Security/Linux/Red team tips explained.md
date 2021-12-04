# Linux Red Team Tips Explained

## GRSEC

## Fail2Ban

Fail2Ban provides an automated way to block suspicious and brute-force logins to a system. This is done by reading log files on a given system and using different in-built and custom scripts to ban offending hosts / IPs. F2B is written in Python and should work on most linux systems.

## PHP Hardening

## SETUID

- Binaries

## Authentication Logs

Linux will write specific logs to specific places under (normally) standard paths such as ```/var/log/```. System authentication logs can normally be found under `/var/log/auth.log` and `/var/log/secure`. Depending on the system there may more more logs or they may be in different places. 

Besides the linux system authentication logs (which are normally part of PAM (pluggable authentication module) authentication). Many services may provide their own logs with authentication information inside them. 


## Process Lists

## User / Service Enumeration & Monitoring

## IPSTATE / NETSTAT / TCPview - Network and connection monitoring

## watch tripwire OSSec - File Integrity Logging

## watch / md5sum - Directory / Filesystem monitoring

- /tmp/

- /etc/

- .ssh/

- passwd, shadow, sudoers


## Immutable file extended/extra file attributes

- chatter

- lsattr


## Network hardening

- ipv6

- firewalls

- CAPRICA
  
- outboud connections