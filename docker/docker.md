---
tags: []
---

to list all images:
```bash
docker images
```

Remove all docker images:
```bash
docker rmi $(docker images -a -q) -f
```

List all docker Containers:
```bash
docker ps
```

Stop All Docker Containers
```bash
docker stop $(docker ps -aq)
```

Remove all docker Containers:
```bash
docker rm $(docker ps -a -q)
```

Restart Docker Service
```bash
sudo systemctl restart docker
```

Check if docker daemon is running:
```bash
systemctl status docker
```

Start docker daemon:
```bash
systemctl start docker
```

Run docker image:
```bash
docker run --rm -it nvim-computer bash
```

Pull docker image:
```bash
docker pull <image>
```

Check for logs of specific container:
```bash
docker-compose logs -f app
```
