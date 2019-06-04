# docker

Install docker from the default CentOS 7 repository
After logging into the server, install the latest version of Docker using yum.


     $ sudo yum -y install docker


          [cloud_user@ip-10-0-1-219 ~]$ sudo yum -y install docker
          [cloud_user@ip-10-0-1-219 ~]$ sudo -i
          [root@ip-10-0-1-219 ~]# groupadd docker
          [root@ip-10-0-1-219 ~]# usermod -aG docker cloud_user
          [root@ip-10-0-1-219 ~]# systemctl enable --now docker



enable & start docker service
Once installation completes, enable & start the service using systemd.

     $ systemctl enable docker
     $ systemctl start docker

user permissions
Create a new group named docker, then add the cloud_user user to the group.

     $ sudo groupadd docker
     $ sudo usermod -aG docker cloud_user
     hello-world

After starting *& enabling Docker, run the hello-world container image to verify installation.

           $ docker run docker.io/hello-world

pull images
After getting a valid return message from the hello-world image, pull the following images into your Docker repository to prepare for the next exercise.

     06kellyjac/nyancat
     jeremy646/doge

     docker pull 06kellyjac/nyancat
     docker pull jeremy646/doge

start static website 

       [root@ip-10-0-1-85 ~]# docker run -d --name treatseekers -p 80:80 spacebones/dog                                                                                                             


--------------------------------------------------------------------------------
#Lab
--------------------------------------------------------------------------------

    login as: cloud_user
    Using keyboard-interactive authentication.
    Password:
    
     [cloud_user@ip-10-0-1-219 ~]$ sudo yum -y install docker
     
              [cloud_user@ip-10-0-1-219 ~]$ sudo -i
              [root@ip-10-0-1-219 ~]# groupadd docker
              [root@ip-10-0-1-219 ~]# usermod -aG docker cloud_user
              [root@ip-10-0-1-219 ~]# systemctl enable --now docker
              
Created symlink from /etc/systemd/system/multi-user.target.wants/docker.service to /usr/lib/systemd/system/docker.service.

      [root@ip-10-0-1-219 ~]# docker ps
      
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
[root@ip-10-0-1-219 ~]# cocker pull docker.io/hello-world
-bash: cocker: command not found

         [root@ip-10-0-1-219 ~]# docker images
         
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
        
        [root@ip-10-0-1-219 ~]# docker run hello-world
        
Unable to find image 'hello-world:latest' locally
Trying to pull repository docker.io/library/hello-world ...
latest: Pulling from docker.io/library/hello-world
1b930d010525: Pull complete
Digest: sha256:0e11c388b664df8a27a901dce21eb89f11d8292f7fca1b3e3c4321bf7897bffe
Status: Downloaded newer image for docker.io/hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

      [root@ip-10-0-1-219 ~]# docker ps -a
      
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
7d36eb50dacd        hello-world         "/hello"            19 seconds ago      Exited (0) 19 seconds ago                       competent_sinoussi

     [root@ip-10-0-1-219 ~]# docker pull 06kellyjac/nyancat
     
Using default tag: latest
Trying to pull repository docker.io/06kellyjac/nyancat ...
latest: Pulling from docker.io/06kellyjac/nyancat
426d0742acee: Pull complete
Digest: sha256:40089cdd1e2468059d009ccb42fb1b248635bccb315e2c790e7c8fa56d107d4e
Status: Downloaded newer image for docker.io/06kellyjac/nyancat:latest


      [root@ip-10-0-1-219 ~]# docker pull jeremy646/doge
      
      
Using default tag: latest
Trying to pull repository docker.io/jeremy646/doge ...
latest: Pulling from docker.io/jeremy646/doge
f17d81b4b692: Pull complete
d5c237920c39: Pull complete
a381f92f36de: Pull complete
e97c3dca5ef2: Pull complete
2f59235a79ff: Pull complete
9f76d2956483: Pull complete
Digest: sha256:bffb378d475d50994c14ed155988c5a8b406d194e9c8806cf6ef4bf480447002
Status: Downloaded newer image for docker.io/jeremy646/doge:latest
[root@ip-10-0-1-219 ~]#
