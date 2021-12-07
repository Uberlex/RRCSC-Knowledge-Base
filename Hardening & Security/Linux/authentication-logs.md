# Authentication Logs

CentOS `/var/log/secure` valid login example.

```shell
Dec  6 12:00:00 <HOSTNAME> sshd[1509387]: Accepted password for root from <CONNECTING HOST> port 31273 ssh2
Dec  6 12:00:00 <HOSTNAME> sshd[1509387]: pam_unix(sshd:session): session opened for user root by (uid=0)

```

Ubuntu `/var/log/auth.log` valid login example.

```shell
Dec  6 12:00:00 <HOSTNAME> sshd[1146601]: Accepted password for root from <CONNECTING HOST> port 1181 ssh2
Dec  6 12:00:00 <HOSTNAME> sshd[1146601]: pam_unix(sshd:session): session opened for user root by (uid=0)

```

As you can see they are the same.
