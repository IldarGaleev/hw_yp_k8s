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