# docker

Install docker from the default CentOS 7 repository
After logging into the server, install the latest version of Docker using yum.

$ sudo yum -y install docker
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

