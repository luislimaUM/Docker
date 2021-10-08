# Docker Learning


Tutorial to learn docker concepts 

Image repository: 
https://hub.docker.com/ 

Commands:<br/>
docker images -- see the images that i have locally
docker pull <image><br/> -- pull the image to local environment
docker run <image> -- if it can't find the image locally it pulls the image from the repository, create a new container from an image<br/>
docker run -d <image> -- run image in detach mode (run in background)<br/>
docker ps -- see what containers are running (ps means process status)<br/>
docker stop <idContainer> -- stop container running<br/>
docker start <idContainer> -- start container (docker run is two commands in one, docker pull + docker start), here we are not working with images but only with containers<br/>
docker ps -a -- list running and stopped containers<br/>
docker run --name <nameThatYouWant> <image> -- if we want to add name to the container to be easier then use it instead using idContainer

Image vs Container: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockerImage.PNG)
<br/>

Docker vs VM: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockervsVM.PNG)

Docker only virtualizes application layer and uses the kernel itself (part of the system that communicates with the hardware) while VM virtualizes both application layer and kernel layer.

Container Port vs Host Port: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockerPorts.PNG)

If we have different containers running on the same port we need to bind the host ports to the container ports<br/>
docker run -p<hostPort>:<containerPort> <image>

Debbuging container
docker logs <idContainer><br/>
docker exec -it <idContainer> /bin/bash -- "it" means "interactive terminal <br/>
exit -- to exit terminal inside container <br/>

Note: Most of the container images are based on some lightweight linux distributions so we won't have much of the linux commands or applications installed here (ex: curl command)

