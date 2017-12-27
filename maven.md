## Cli
```bash
mvn clean
mvn package
mvn package -Dmaven.test.skip=true
```

## Proxy
```xml
<settings>
  <proxies>
    <proxy>
      <id>proxy-http</id>
      <active>true</active>
      <protocol>http</protocol>
      <host>proxy.com</host>
      <port>8080</port>
      <username>username</username>
      <password>password</password>
      <nonProxyHosts>localhost|127.0.0.1</nonProxyHosts>
    </proxy>
    <proxy>
      <id>proxy-https</id>
      <active>true</active>
      <protocol>https</protocol>
      <host>proxy.com</host>
      <port>8080</port>
      <username></username>
      <password></password>
      <nonProxyHosts>localhost|127.0.0.1</nonProxyHosts>
    </proxy>
  </proxies>
</settings>
```
