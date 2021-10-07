# Docker Learning


Tutorial to learn docker concepts 

Image repository: 
https://hub.docker.com/ 

Commands:<br/>
docker pull <image><br/>
docker run <image> -- if it can't find the image locally it pulls the image from the repository<br/>
docker ps -- see what containers are running (ps means process status)<br/><br/>

Image vs Container: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockerImage.PNG)
<br/>

Docker vs VM: <br/>
![alt text](https://github.com/luislimaUM/Docker/blob/main/dockervsVM.PNG)

Docker only virtualizes application layer and uses the kernel itself (part of the system that communicates with the hardware) while VM virtualizes both application layer and kernel layer.
