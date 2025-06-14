WORKDIR
The main use of the WORKDIR is to change the working directory while running any docker commands. Instead of using cd /directory_path WORKDIR should be used so that the docker container will run the given commands in the required directory.
FROM almalinux:9
RUN mkdir /app
RUN cd /app
RUN pwd
USER test
CMD [ "sleep","100"]
#Once this docker image is created and a docker container out of it the terminal will be into the /app directory.