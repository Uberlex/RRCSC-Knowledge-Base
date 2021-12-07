# Network Monitoring

Disable IPv6 >:(


## LISTEN vs ESTABLISHED


`LISTEN means that the socket is ready and waiting for a connection.

`ESTABLISHED` means that there is currently a connection to the socket.

A service with a port on `LISTEN` will create an `ESTABLISHED` connection once a client connects to it. For example SSH will `LISTEN` on port 22 and when a connecton occurs you will see an `ESTABLISHED` connection

The command `netstat -anp | grep 22` will output entries for both `LISTEN` and `ESTABLISHED` on port 22. We see both since there is an SSH server running on the server and there is an active SSH session to a client.

```bash
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN 
```

```bash
tcp        0      0 20.20.20.50:22          10.10.10.204:1029       ESTABLISHED
```

>Note that the first IP belongs to the server and the second belongs to the connecting client.


## View Listening Ports

```bash
netstat -tulpen
```


```bash
 ss -tlunp
```



```bash
netstat -atupen
```

