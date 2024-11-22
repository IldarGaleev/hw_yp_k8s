# Module1

## Task 1

```bash
docker build -t javaapp:ipcounter .
```

```bash
docker run --name ipcounter -v "$(pwd)/ipfile.txt:/app/ipfile.txt:ro" javaapp:ipcounter ipfile.txt true
```

### Output
```bash
ipcounter
Number wrong IP Addresses: 1
Distinct IP Addresses: 3
Time spent: 0s
```

## Task 2

### Prepare PowerShell
```PS
New-Alias -Name k -Value kubectl
$env:KUBECONFIG='.\kubeconfig.yaml'
```

### 1.1 Run pod
```bash
k run tomcat-pod --image=tomcat:9.0.97-jre21 --restart=Never --port=8080
```

### 1.2 Run service
```bash
k expose pod tomcat-pod --name=tomcat-service --port=8080
```

### 2. Service name - "Catalina"

```bash
22-Nov-2024 03:12:00.402 INFO [main] org.apache.catalina.core.StandardService.startInternal Starting service [Catalina]
```

### 3. Web page
<hr class="line" />


<html lang="ru"><body><h1>HTTP Status 404 – Не найдено</h1><hr class="line" /><p><b>Type</b> Status Report</p><p><b>Description</b> The origin server did not find a current representation for the target resource or is not willing to disclose that one exists.</p><hr class="line" /><h3>Apache Tomcat/9.0.97</h3></body></html>

<hr class="line" />

### 4. Environments value

Name|Value
-:|-
CATALINA_HOME|'/usr/local/tomcat'
HOSTNAME|'tomcat-pod'
JAVA_HOME|'/opt/java/openjdk'
KUBERNETES_PORT_443_TCP_PROTO|'tcp' 
LANG|'en_US.UTF-8'
