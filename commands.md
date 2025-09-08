
**How to remove all docker container:**
```bash
docker rm -f $(docker ps -a -q)
```

**How to remove all docker images:**
```bash
docker rmi -f $(docker images -q)
``` 

**How to remove all docker volumes:**
```bash
docker volume rm $(docker volume ls -q)
```

**How to remove all docker networks:**
```bash
docker network rm $(docker network ls -q)
```
