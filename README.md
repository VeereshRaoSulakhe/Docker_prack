# Docker_prack
This is the repo setup for the handy information on Docker images and setup instructions
docker create <image>:tag  ->For creating a image
docker pull ngnix <tag like latest or specific version>
docker ps to list the containers
docker ps -a to list all the containers with any status
docker rm <container_id> to remove a container
ocker rm -f <container_id> to forcefully remove a container
dDocker rmi docker images -a -q to delete all the docker images
docker rmi docker ps -a -q
docker run <image> to run a container using image
docker run -d <image> to run a container in detached mode.
A server contains 65535 ports

Accessing a container from internet:
For accessing a container from the internet we need to enable the ports for the server and the container.
docker run -d -p 8000:80 ngnix
#Here 8000 is the host port and the 80 port is the container port 

Docker image == base OS + application runtime + system dependencies + application dependencies
FROM is used to give the reference of the O/S to be used while creating a docker image.
FROM image-name:tag

Remove commands for the docker containers:
Docker rm -f `docker ps -a -q`  ->used to remove all the running containers in the current server.
Docker rmi `docker images -a -q`  --> used to remove all the images in the server.

Pushing a docker image from a local instance to docker hub.
To push an image to a docker repository first we need to login to docker hub and then push the image as below.
Docker push <dockerusername>/<image_name>:tag
This will push the docker image to the docker repository.

Pulling a docker image from a docker hub:
To pull an image from docker hub we need to use below format
Docker pull <dockerusername>/<image_name>:tag

