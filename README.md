# cf-docker
# Getting Started on Pushing Docker Images to CF
# Here is a cheat sheet on how to do it.

1. First Install the Docker Toolbox on you Mac.
https://docs.docker.com/mac/step_one/

2. Start the Docker Terminal from your Launchpad. This will start the docker virtual machine.

TEST:
$docker run hello-world
$docker run -it ubuntu bash

3. Login to Docker Hub

$docker login

You Authentication credentials will be stored in  ~/.docker/config.json

4. Search and Pull an Image
$docker search centos
$docker pull centos
$docker images

5. Create a Repository on Docker Hub
https://hub.docker.com/

6. Create a Docker File and Build a Docker Image
https://docs.docker.com/examples/nodejs_web_app/

$docker build -t rjain15/centos-node-hello .

7. Push it in the Repo

$docker push rjain15/centos-node-hello

8. Pull it down from Repo
$docker pull rjain15/centos-node-hello

9. Get the IP Address of you local Docker VM
$docker-machine ls
NAME      ACTIVE   DRIVER       STATE     URL                         SWARM

default   *        virtualbox   Running   tcp://192.168.99.100:2376   

10. Testing it locally

$docker run -d -P --name web rjain15/centos-node-hello
$docker ps

11. To get the Local Port Number
$docker port web

8080/tcp -> 0.0.0.0:32768

http://192.168.99.100:32768

12. Push docker image to cf

cf push --docker-image rjain15/centos-node-hello
