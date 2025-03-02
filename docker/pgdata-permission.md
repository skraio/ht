Change ownership of the pgdata directory to match the user running the Docker process:
```bash
sudo chown -R $(whoami):$(whoami) pgdata
```


```bash
sudo chown -R 1000:1000 ./pgdata
```

```yaml
postgres:
    image: postgres:latest
    user: 1000:1000
```
