Docker file:  Is the file which is a configuration file of a docker image in which we can write the custom docker image configuration and create image out of it.

Docker image == base OS + application runtime + system dependencies + application dependencies

Dockerfile -> create a docker file with this name and give the configuration as below.

FROM is used to give the reference of the O/S to be used while creating a docker image.
FROM image-name:tag
FROM almalinux:9