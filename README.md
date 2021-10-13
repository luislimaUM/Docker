# Docker Learning


Tutorial to learn docker concepts 

Image repository: 
https://hub.docker.com/ 

Commands:<br/>
<strong>docker images</strong>--see the images that i have locally<br/>
<strong>docker pull {image}</strong> --pull the image to local environment<br/>
<strong>docker run {image}</strong> --if it can't find the image locally it pulls the image from the repository, create a new container from an image<br/>
<strong>docker run -d {image}</strong> --run image in detach mode (run in background)<br/>
<strong>docker ps</strong> --see what containers are running (ps means process status)<br/>
<strong>docker stop {idContainer}</strong> --stop container running<br/>
<strong>docker start {idContainer}</strong> --start container (docker run is two commands in one, docker pull + docker start), here we are not working with images but only with containers<br/>
<strong>docker ps -a</strong> --list running and stopped containers<br/>
<strong>docker run --name {nameThatYouWant} {image}</strong> --if we want to add name to the container to be easier then use it instead using idContainer

Image vs Container: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockerImage.PNG)
<br/>

Docker vs VM: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockervsVM.PNG)

Docker only virtualizes application layer and uses the kernel itself (part of the system that communicates with the hardware) while VM virtualizes both application layer and kernel layer.

Container Port vs Host Port: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockerPorts.PNG)

If we have different containers running on the same port we need to bind the host ports to the container ports<br/>
<strong>docker run -p{hostPort}:{containerPort} {image}</strong>

Debbuging container<br/>
<strong>docker logs {idContainer}</strong> --see container logs<br/>
<strong>docker exec -it {idContainer} /bin/bash</strong> --"it" means "interactive terminal, open terminal inside container <br/>
<strong>exit</strong> --to exit terminal inside container <br/>

Note: Most of the container images are based on some lightweight linux distributions so we won't have much of the linux commands or applications installed here (ex: curl command)<br/><br/>
Demo commands: <br/>
<strong>docker pull mongo</strong> <br/>
<strong>docker pull mongo-express</strong> <br/>
<strong>docker network ls -- list networks</strong> <br/>
<strong>docker network create mongo-network</strong> -- create network to connect mongo to mongo-express (mongo-express is UI to manage mongoDB) <br/>
<strong>docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo</strong> -- run the mongo container, -e is environmental variable, username and password replace the default ones and set the name and network of the container. (this variables is in docker hub mongodb documentation)<br/>
<strong>docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=pass --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express</strong><br/>

Docker Compose<br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockercompose.PNG)<br/>
