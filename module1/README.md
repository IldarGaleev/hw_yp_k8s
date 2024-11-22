# Module1

## 1

```bash
docker build -t javaapp:ipcounter .
```

```bash
docker run --name ipcounter -v "$(pwd)/ipfile.txt:/app/ipfile.txt:ro" javaapp:ipcounter
```