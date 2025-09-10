In this example, we only write `docker run` command in the form of `docker-compose`.


```bash
sudo apt install docker.io docker-compose -y
```


```bash
sudo docker run --name web -itd -p 8080:80 nginx 
```

---

```bash
vim docker-compose.yaml
```

```bash
version: '3'
services:
    website:
        image: nginx
        ports:
            - "8081:80"
        restart: always
```


```bash
sudo docker-compose up -d
```


```bash
sudo docker ps
```

```bash
sudo docker-compose ps
```

```bash
localhost:8081
```

```bash
sudo docker-compose down
```


