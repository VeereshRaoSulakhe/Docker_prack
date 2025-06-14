USERS
Containers should not be let to run with Root access.

FROM almalinux:9
RUN adduser test
USER test
CMD [ "sleep","100"]

In the above script a new test user is added to the container and the command of sleep for 100s is given by the test user itself.
docker build -t userimage:1.1 .
docker run -d userimage:1.1
docker exec -it 56852c1c8213 bash
Now when we enter into the container we will be into the user which is being used by the container