COPY Instruction
This instruction is used to copy a code file into the docker image while building it.
---------------------
FROM almalinux:9
RUN dnf nginx -y
RUN rm -rf usr/share/nginx/html/index.html
COPY index.html usr/share/nginx/html/index.html
------------------------
#Here in this example we are using copy instruction to update the index.html file

COPY v/s ADD instruction
COPY and ADD instructions both will be used to copy files from the workspace while creating a docker image.
Add can directly download content from internet, can Untar the files into the image.
