In this lab, we create a container using `host network type`. Afterthat, when we inspect and see IPAddress, there will be no IPAddress there.


## Create container using *host network type*
```bash
docker run -itd --name host-demo --network=host nginx:latest
```

### Inspect container:
```bash
docker inspect host-demo 
```

IPAddress: `""` 


You will see that the networking is host what is the IP address? 

There is no custom IP address here because it is binded with the host networking itself. So, Docker did not create any virtual network in this case because directly you are able to access this container using the host itself the host IP address itself. 







---
---
