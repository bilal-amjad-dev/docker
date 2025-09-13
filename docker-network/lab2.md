In this lab, we have 2 containers. One is running in default bridge network and other is running in our custom bridge network. When we ping in living in one container, we will not be able to reach other container.

# Create network 



```bash
docker network create secure-network 
```

(It is a custom bridge network.)


## Run a container **with your created network**:


```bash
docker network -itd --name finance --network secure-network nginx:latest
```

### Inspect *finance* container (view the IP address of *finance* container):

```bash
docker inspect finance 
```

See IPAddress: `172.19.0.2`




### Inspect *logout* container (view the IP address of *logout* container):


```bash
docker inspect logout
```



You will notice that here inside the networks, previously whenever I was showing you for the network of login container, it says as bridge but here it is seeing as secure network because we have allocated data dynamic.


You cna see *Both containers have different ip addresses* because both have different **bridge** network.



# Ping

(We can ping because we have installed ping in 1st container.)

```bash
docker exec -it login /bin/bash 
```

```bash
ping 172.19.0.2
```


You will see that you will not able to reach the *finance container*. So, this is how you will make your container secure using the concept of networking.
