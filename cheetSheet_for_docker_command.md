This cheetsheet will help you to basic docker commands




1) Finding the version

 how to find the installed docker version.

hellodev$ docker --version

Docker version 19.03.5, build 633a0ea




2) Downloading image

pull the Apache HTTP server image.

hellodev$ docker pull httpd



3) Images
List all the docker images pulled on the system with image details such as TAG/IMAGE ID/SIZE etc.

hellodev$ docker images

REPOSITORY                 TAG                 IMAGE ID            CREATED             SIZE

httpd                      latest              ee39f68eb241        2 days ago          154MB

hello-world                latest              fce289e99eb9        6 months ago        1.84kB

sequenceiq/hadoop-docker   2.7.0               789fa0a3b911        4 years ago         1.76GBCopy


4) Run

This command will create a docker container in which the Apache HTTP server will run.

hellodev$ docker run -it -d httpd

09ca6feb6efc0578951a3e28764345678909876543349703eb54d975930fe6eCopy


5) What’s running?

ps lists all the docker containers are running with container details.

hellodev$ docker ps

CONTAINER ID        IMAGE               COMMAND              CREATED             STATUS              PORTS               NAMES

09ca6feb6efc        httpd               "httpd-foreground"   36 seconds ago      Up 33 seconds       80/tcp              suspicious_bellCopy


6) ps -a
List docker containers running/exited/stopped with container details.

hellodev$ docker ps -a

CONTAINER ID        IMAGE                            COMMAND                  CREATED             STATUS                     PORTS                                                                                                                                NAMES

09ca55446efc        httpd                            "httpd-foreground"       51 seconds ago      Up 49 seconds              80/tcp                                                                                                                               suspicious_bell

4433b3381078        sequenceiq/hadoop-docker:2.7.0   "/etc/bootstrap.sh -d"   2 weeks ago         Exited (137) 9 days ago                                                                                                                                         quizzical_raman




7) exec
I am accessing the apache server container in this example.

``hellodev$ docker exec -it 09ca6mar6efc bash```

root@09ca6feb6efc:/usr/local/apache2# ls

bin  build  cgi-bin  conf  error  htdocs  icons  include  logs                modules



8) Removing container
Remove the docker container with container id mentioned in the command.

hellodev$ docker rm 9b6343d3b5a0

9b6343d3b5a0Copy
Run the below command to check if the container got removed or not.

hellodev$ docker ps -a

CONTAINER ID        IMAGE                            COMMAND                  CREATED              STATUS                     PORTS                                                                                                                                NAMES

09ca6feb6efc        httpd                            "httpd-foreground"       About a minute ago   Up About a minute          80/tcp                                                                                                                               suspicious_bell



9) Removing image
Remove the docker image with the docker image id mentioned in the command

hellodev$ docker rmi fce289e99eb9

Untagged: hello-world:latest

Untagged: hello-world@sha256:41a65640635t435797875322592bf4ddb09cb2f1e02147c6ed8



10) Restart Docker

Restart the docker container with container id mentioned in the command.

hellodev$ docker restart 09ca6feb6efc


Run the command below and check the STATUS parameter to verify if the container started recently.

hellodev$ docker ps

CONTAINER ID        IMAGE               COMMAND              CREATED             STATUS              PORTS               NAMES

09ca6feb6efc        httpd               "httpd-foreground"   6 minute
