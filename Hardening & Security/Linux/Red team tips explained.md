# Linux Red Team Tips Explained

## GRSEC

## Fail2Ban

Fail2Ban provides an automated way to block suspicious and brute-force logins to a system. This is done by reading log files on a given system and using different in-built and custom scripts to ban offending hosts / IPs. F2B is written in Python and should work on most linux systems.

[More Fail2Ban information can be found in this link](Fail2Ban.md)

## PHP Hardening
PHP itself may not be insecure but many implementations of applications using PHP are. For instance lookup 'wordpress php vulnerabilities' and there will be many examples of bad implementation over the years. Expect issues to exist with any php.ini files. Inderstand the options and fix them.

[More PHP information can be found in this link](php.md)

## SETUID / SUID / SGID / Sticky

Special permissions can cause many different security holes. The filesystem should be enumerated and these special permissions should be validated.

[More SETUID information can be found in this link](setuid.md)

## Authentication Logs

Linux will write specific logs to specific places under (normally) standard paths such as ```/var/log/```. System authentication logs can normally be found under `/var/log/auth.log` and `/var/log/secure`. Depending on the system there may more more logs or they may be in different places. 

Besides the linux system authentication logs many services may provide their own logs with authentication information inside them.

Redhat based systems will log authentication messages to `/var/log/secure`
Debian based systems will log authentication messages to `/var/log/auth.log`

[More authentication log information can be found in this link](authentication logs.md)

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