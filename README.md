#docker-stunnel

##Setup

 - replace stunnel.pem (this is a self signed temporary cert for localhost)
 - update stunnel.conf
 - build container
 - You must run the container via: `echo "stunnel /etc/stunnel/stunnel.conf" | docker run-i -t moot/stunnel /bin/bash` to avoid the problem below

##Problems


This works:
 ```
 docker run -i -t moot/stunnel /bin/bash  
 stunnel /etc/stunnel/stunnel.conf

 OR

 echo "stunnel /etc/stunnel/stunnel.conf" | docker run-i -t moot/stunnel /bin/bash
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
