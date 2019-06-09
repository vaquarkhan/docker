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


------------------------------------------

          docker pull centos:6
          
Once the pull completes, start the Docker container in interactive mode, name it 'websetup'.

            docker run -it --name websetup centos:6 /bin/bash
            
Update the system, then install Apache & Git.

       yum -y update
       yum -y install httpd git
       
Once installation completes, clone the content-dockerquest-spacebones repository, then copy the contents of the /doge/ subdirectory to /var/www/html.

         git clone https://github.com/linuxacademy/content-dockerquest-spacebones
         
        cp content-dockerquest-spacebones/site /var/www/html
        
In order for the site to display correctly, rename the default welcome.conf file to welcome.conf.bak.

       mv /etc/httpd/conf.d/welcome.conf /etc/httpd/conf.d/welcome.conf.bak
       
Enable & start the Apache service, then exit the container environment by typing exit or hitting CTRL+C.

           chkconfig httpd on && service httpd start
           exit
           
Save the edited image, then pat yourself on the back for being awesome.

         docker commit websetup spacebones:thewebsite
 
 -----------------------------
 # create postgress image 
 
 
        docker create -v /data --name boneyard spacebones/postgres /bin/true
        docker run -d --volumes-from boneyard --name cheese spacebones/postgres
        docker run -d --volumes-from boneyard --name tuna spacebones/postgres
        docker run -d --volumes-from boneyard --name bacon spacebones/postgres


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
      
      ----------------------------
      # Lab 2
      
      Learning Objectives
      check_circle
      Create the Dockerfile
      keyboard_arrow_up
      Create a Dockerfile:

    vi Dockerfile
    
    The Dockerfile should contain the following:

FROM node

              RUN mkdir -p /var/node

      ADD content-express-demo-app/ /var/node/
      WORKDIR /var/node
      RUN npm install
      CMD ./bin/www
      check_circle
   
    Build the Docker Image
    keyboard_arrow_up
     Build the Docker image:

     docker build -t USERNAME/express -f Dockerfile .

check_circle
Push the Image to Docker Hub
keyboard_arrow_up
Login to Docker Hub:

      docker login
      
Push the image to Docker Hub:

     docker push USERNAME/express
     
check_circle
Create a Demo Container
keyboard_arrow_up
Create the container that Watchtower will monitor:

            docker run -d --name demo-app -p 80:3000 --restart always USERNAME/express
            
check_circle
Create the Watchtower Container
keyboard_arrow_up
Create the Watchtower container that will monitor the demo-app container:

         docker run -d --name watchtower --restart always -v /var/run/docker.sock:/var/run/docker.sock v2tec/watchtower -i 30

check_circle
Update the Docker Image
keyboard_arrow_up
Update the Docker image:

         docker build -t USERNAME/express -f Dockerfile .

Repush the image to Docker Hub:

     docker push USERNAME/express:latest

