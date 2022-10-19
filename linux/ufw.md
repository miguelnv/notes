Hardened raspberry pi config

1. Active server connections
```
> sudo netstat -nltup
```

2. UFW Rules
```
> sudo ufw default deny incoming	
> sudo ufw allow from 192.168.1.0/24 to any port 22 proto tcp  -> allow only local lan requests to port 22 (ssh)
> sudo ufw allow from 192.168.1.0/24 to any port 53 proto udp  -> dns port
> sudo ufw allow from 192.168.1.0/24 to any port 53 proto tcp  -> dns port
> sudo ufw allow from 192.168.1.0/24 to any port 67 proto udp  -> dhcp port
> sudo ufw allow from 192.168.1.0/24 to any port 68 proto udp  -> dhcp port
```

