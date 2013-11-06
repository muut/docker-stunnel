#docker-stunnel
==============

##Setup

 - replace stunnel.pem (this is a self signed temporary cert for localhost)
 - update stunnel.conf
 - build container


##Problems


This works:
 ```
 docker run -i -t moot/stunnel /bin/bash  
 stunnel /etc/stunnel/stunnel.conf
 ```

Either of these however:
```
docker run -i -t moot/stunnel stunnel /etc/stunnel/stunnel.conf
OR
docker run -i -t moot/stunnel
```
results in:
```
[error] commands.go:1993 Error resize: Error: bad file descriptor 
```