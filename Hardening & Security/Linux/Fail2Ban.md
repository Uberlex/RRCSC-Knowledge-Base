# Install

Fail2Ban should be available via the package manager of most linux systems

## Debian 
```shell
sudo apt-get install fail2ban
```

## Redhat
Redhat requires the epel repository which contains more software and more up-to-date software
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

[How To Protect SSH With Fail2Ban on CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-protect-ssh-with-fail2ban-on-centos-7)