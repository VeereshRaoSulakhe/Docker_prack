Argument instruction is used when we want to execute a specific version while creating the docker image instead of having a default version.

ARG version
FROM almalinux:${version}
Docker build -t arg:v1.0 --build-arg version=8

This will run the docker image on almalinux:8 version.

This will be used while creating an image.
While writing a docker file we can use arguments and pass the arguments through command line while building an image, we can also give default values so that whenever there are no values passed it can consider default values and execute.