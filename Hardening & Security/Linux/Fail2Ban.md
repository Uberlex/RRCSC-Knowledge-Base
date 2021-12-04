# Install

Fail2Ban should be available via the package manager of most linux systems

## Debian 
```shell
sudo apt-get install fail2ban
```

### Configuration locations

|term|description|
|----|-----------|
|filter	|a filter defines a regular expression which must match a pattern corresponding to a log-in failure or any other expression|
|action	|an action defines several commands which are executed at different moments|
|jail	|a jail is a combination of one filter and one or several actions. Fail2ban can handle several jails at the same time|
|client	|refers to the script fail2ban-client|
|server	|refers to the script fail2ban-server|


## Redha|Redhat requires the epel repository which contains more software and more up-to-date software
```shell
sudo yum install epel-release -y
sudo apt-get install fail2ban
sudo systemctl enable fail2ban
```

### Configuration locations

```shell
/etc/fail2ban/
```

# Use

# Source resources

[Fail2Ban Documentation Manual](https://www.fail2ban.org/wiki/index.php/MANUAL_0_8)

[How To Protect SSH With Fail2Ban on CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-protect-ssh-with-fail2ban-on-centos-7)