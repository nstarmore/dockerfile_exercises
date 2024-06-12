# DockerfileExercise

## Task 1 
This is a basic Flask application that serves a simple static website that returns the machine's hostname.

It is directly accessible on port 5500.

Set the environment variable YOUR_NAME to your name to have the app display your name in its welcome message. Otherwise, it will refer to you as "friend".

The nginx.conf file can be used to configure an NGINX container to run as a reverse proxy to the Flask app container, effectively making the Flask application accessible on port 80. You will need to know how to configure networks in Docker in order to achieve this.

## Task 2
Two tier application with a mysql database and a flask app that serves a simple static website.

MySQL requires root password to be added to Dockerfile, look through the MySQL Docker image docs for information. 

A bind mount should be used to move the createTabkle.sql into the container

app.py requires the mysql password to be added to line 8 replacing [PASSWORD]

## Useful Docker Commands
sudo gpasswd -a <username> docker - add user to docker group
docker images - list images available on host
docker inspect - give details on instance
docker ps - list docker processes
docker ps -a - list all docker processes that have run/available
docker run -d <dockername> - run docker in background
docker run -d -p <portvm>:<portcontainer> <containerid/dockername> - run in background and map to
 same port as the container is running (port publish)
docker run -d --name <givecontainername> <imagename> - run in background and give specific name to local container
docker stop <containerid/dockername> - stop container
docker rm <containerid/dockername> - delete container
docker stop $(docker ps -q) && docker rm $(docker ps -aq) - stop all containers from running and remove all of the containers
docker run -d --network <networkname> <imagename> - run cotnainer and connect to network
