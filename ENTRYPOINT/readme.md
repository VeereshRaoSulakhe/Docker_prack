FROM almalinux:9
CMD [ "ping","-c5","google.com" ]

When the docker image is created using docker build -t entrypointimage:1.0 .
It will create the docker image successfully.
When the docker run command is give as "docker run entrypointimage:1.0" It will run the container as well as ping google.com 5times.
However when we use "docker run entrypointimage:1.0 ping -c6 yahoo.com" it will override the command given in the CMD instruction.

When ENTRYPOINT is used you cannot ovverite the CMD instruction passed in a container when it is given as below.

FROM almalinux:9
ENTRYPOINT [ "ping","-c5","google.com" ]

CMD V/S ENTRYPOINT
You can mix CMD and ENTRYPOINT for better results 
CMD is used to supply default arguments for the entrypoint and the arguments given in ENTRYPOINT cannot be overridden.
We can always overwrite the arguments given in the CMD instruction during run time.
FROM almalinux:9
CMD [ "google.com" ]
ENTRYPOINT [ "ping","-c5" ]

Docker run entrypointimage:1.0.0 yahoo.com
When the docker run is given as above it will ping yahoo.com 5 times instead of pingging google.com
