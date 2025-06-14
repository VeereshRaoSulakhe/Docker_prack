CMD instruction 
This is used to give the commands to be run in a container when it is getting created.
Systemctl will not work in containers.
Below is the example of the CMD run for nginx
CMD ["nginx","-g","deamon off;"]
RUN V/S CMD:
Run executes at the time of docker image creation
CMD executes at the time of container creation.