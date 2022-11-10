# jenkins-agent-ssl-fix
private-certificate

```
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -sha256 -days 365 -nodes
openssl x509 -in cert.pem -out cert.der -outform DER
keytool -importcert -alias local-CA   -keystore /etc/ssl/certs/java/cacerts   -file cert.der   -storepass changeit
```

Done !
