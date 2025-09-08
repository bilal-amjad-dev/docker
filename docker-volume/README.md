
**Docker containers is ephemeral**

What does this mean? If the container is deleted the data on that container residing on that container would be deleted


**Docker volumes offer persistent storage** 

What does it mean? Docker volumes are required to store data outside the containers so it means that whether our containers are failed or lost or crashed our data would be saved


**/var/lib/docker**

What does it mean? when we install Docker a dedicated directory is created.


```bash
/var/lib/docker
            ├── volume
            ├── network
            └── images
```
  

So everything we create in Docker for instance 
- we create a Docker volume that Docker volume will be created here and 
- if we could create a network it would be saved here 
- the docker images are saved


**docker volume create**
```bash
docker volume create volume-name
```

**We have 2 options to store data**

- docker volumes
- bind mounts



> Preferred: volumes because volumes are completely managed by Docker itself. 


|Docker Volumes|Bind Mounts|
|---|---|
|Volumes are independent we can create uh volumes and we can attach them anywhere|We are dependent of our underlying operating system|
|Volumes are completely managed by Docker itself|Bind mounts may be stored anywhere on the host system|
|Volumes are stored in a part of the host filesystem which is managed by Docker (/var/lib/docker/volumes/)|You can store bind mounts anywhere on the host system|
|Volumes can be easily backed up or migrated|Bind mounts are dependent on the directory structure and OS of the host machine|
|Volumes work on both Linux and Windows containers|Bind mounts have limited functionality on Windows containers|

