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

## Immutable file extended/extra file attributes

- chatter

- lsattr

## File Timestamps

Files have timestamps for when they were created, accessed, and modified. Compare timestamps to look for suspicous dates. atime and mtime can both be changed while ctime is harder to change it is still possible.

Change `atime` of a file.

```shell
touch -a --date="1988-02-15 01:00:17.547775198 +0300" <FILE>
```

Change `mtime` of a file.

```shell
 touch -m --date="2020-01-20 23:05:43.443117094 +0400" <FILE>
```

Change file date (shows with ls)

```shell
touch -d "-48 hour" <FILE>
```

Look into normal file timestamps EG: access/modify/change times being the same or not depending on if the file was edited/viewed/moved etc.

If access / change are the same but modified is different the file may have been copied from another system

If changed time is the newer time then the modification of the file is probably a permission / owner / attribute but not file contents.

[MITRE - Indicator Removal on Host: Timestomp ](https://attack.mitre.org/techniques/T1070/006/)

## Authentication Logs

Linux will write specific logs to specific places under (normally) standard paths such as ```/var/log/```. System authentication logs can normally be found under `/var/log/auth.log` and `/var/log/secure`. Depending on the system there may more more logs or they may be in different places. 

Besides the linux system authentication logs many services may provide their own logs with authentication information inside them.

Redhat based systems will log authentication messages to `/var/log/secure`
Debian based systems will log authentication messages to `/var/log/auth.log`

[More authentication log information can be found in this link](authentication-logs.md)

## Process Lists

## User / Service Enumeration & Monitoring

## IPSTATE / NETSTAT / TCPview - Network and connection monitoring

Monitoring connections to and from a linux system can help you determine if someone has breached your system or if you have some sort of malware calling home for instructions / data exfil. 

There are many tools that you can use to monitor connections. 

[More information about network monitoring can be found in this link]](network-monitoring.md)

## watch tripwire OSSec - File Integrity Logging

## watch / md5sum - Directory / Filesystem monitoring

- /tmp/

- /etc/

- .ssh/

- passwd, shadow, sudoers


## Network hardening

- ipv6

- firewalls

- CAPRICA
  
- outboud connections