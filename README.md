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

      [root@ip-10-0-1-85 ~]# docker run -d --name treatseekers2 -p 88:88 spacebones/doge

now type server ip ini browser will see browser static website

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
        
      [root@ip-10-0-1-219 ~]# docker ps -a
      
     CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
     7d36eb50dacd        hello-world         "/hello"            19 seconds ago      Exited (0) 19 seconds ago                               competent_sinoussi

     [root@ip-10-0-1-219 ~]# docker pull 06kellyjac/nyancat
     


      [root@ip-10-0-1-219 ~]# docker pull jeremy646/doge
      
      
