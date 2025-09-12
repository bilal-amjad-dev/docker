
Let's say there is front-end container
and there is a backend container. So, obviously front-end container has to talk to backend container. 

So, there has to be a common way how this container talks to another.

So, that means there has to be a networking way of how one container can talk to the another container (use of IP address)


## Create 1st container

```bash
docker run -itd --name login nginx:latest
```

Exec the container:

```bash
docker exec -it login /bin/bash
```

Install ping:

```bash
apt update

apt-get install iputils-ping -y 

ping -V
```


### Inspect 1st container:
```bash
docker inspect login
```

See IPAddress:
```bash
see IPAddress: 172.17.0.2
```


---


## Create 2nd container

```bash
docker run -itd --name logout nginx:latest
```

Exec the container:
```bash
docker exec -it logout /bin/bash
```


### Inspect 2nd container:
```bash
docker inspect logout 
```
See IPAddress:
```bash
see IPAddress: 172.17.0.3
```

---

## Ping

```bash
docker exec -it login /bin/bash
```
```bash
ping 172.17.0.3
```




