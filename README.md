### Build
* Clone repo
* Execute following commands to build the image:
```
cd sf4-server-docker/sf4-server/

docker build -t skyfactory4:latest .
```

### Initial Run
* Execute following commands to initialize the container:
```
docker volume create minecraft_data

docker run -d -v minecraft_data:/minecraft -it -p 25565:25565 --name sf4_server skyfactory4:latest /bin/bash -c "./ServerStart.sh && tail -f ./eula.txt"
```
* Execute following command to stop the container:
```
docker stop sf4_server
```

### Subsequent Runs
* Execute following command to start the container:
```
docker start sf4_server
```
* Execute following command to stop the container:
```
docker stop sf4_server
```

### Maintenance && Administration
* Execute following command to reach the operator console of the server:
```
docker attach sf4_server
```
* Execute following command to reach the shell inside the container:
```
docker exec -it sf4_server sh
```

