#####ca-base <dir>
用于指定ca证书的存储路径，如证书为/etc/haproxy/ca.crt  
配置文件中如此配置:
```
---
ca-base /etc/haproxy
---
bind *:443 ssl crt server.pem ca-file ca.crt verify required
---
```
