### Lab: Bind Mounts:

In this lab, we create:
- directory 'mkdir'
- `run` container and `bind` directory
- `exec` container
- create file
- see changes in host machine's `directory`

```bash
mkdir testingmount
```

*docker volume list*
```bash
docker volumes ls 
```

*create container and mount a directory*
```bash
docker run -it -d -p 80:80 -v /home/devopsmolvi/testtingmount:/opt --name container1 nginx:latest
```

`sourcedirectory:destinationdirectory`

```bash
docker exec -it 12344321 sh 
```

```bash
cd /opt
```

```bash
touch abc.txt
```

exit

/home/devopsmolvi/testingmount/
ls -l 

