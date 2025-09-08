
### Docker volume lab:

In this docker volume lab, we create:
- `docker volume`,
- `run` container,
- `exec` container,
- do changes,
- and then see changed in host machine `cd /var/lib/docker/volumes/myfirstvolume/_data`.  

*Create docker volume*
```bash
docker volume create myfirstvolume
```

*docker volume list*
```bash
docker volume ls
```

*docker volume inspect*
```bash
docker volume inspect myfirstvolume
```

*/var/lib/docker/volumes*

```bash
cd var/lib/docker/volumes
ls -l
cd myfirstvolume
ls -l
cd _data
ls -l
```

*Run a container with volume attached*
```bash
docker run -it -d -p 80:80 -v myfirstvolume:/opt --name container1 nginx:latest
```

*Exec into container*
```bash
docker exec -it container1 sh
```

*Inside container*
```bash
cd /opt
ls -l
touch abc.txt
ls -l
exit
```

*Check the volume data on host machine*
```bash
cd /var/lib/docker/volumes/myfirstvolume/_data
ls -l
cat abc.txt
```

docker inspect container1 | grep volume 




*We cannot remove a volume if it is attached to any running container*


```bash 
docker rm -f container1
```

```bash
docker volume ls
docker volume rm myfirstvolume
```

