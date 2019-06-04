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

--------------------------------------------------------------------------------
#Lab
--------------------------------------------------------------------------------

    login as: cloud_user
    Using keyboard-interactive authentication.
    Password:
    
     [cloud_user@ip-10-0-1-219 ~]$ sudo yum -y install docker
     
[sudo] password for cloud_user:
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: repos-va.psychz.net
 * extras: repos-va.psychz.net
 * updates: repos-va.psychz.net
base                                                                  | 3.6 kB  00:00:00
extras                                                                | 3.4 kB  00:00:00
updates                                                               | 3.4 kB  00:00:00
(1/4): base/7/x86_64/group_gz                                         | 166 kB  00:00:00
(2/4): extras/7/x86_64/primary_db                                     | 200 kB  00:00:00
(3/4): updates/7/x86_64/primary_db                                    | 5.0 MB  00:00:00
(4/4): base/7/x86_64/primary_db                                       | 6.0 MB  00:00:00
Resolving Dependencies
--> Running transaction check
---> Package docker.x86_64 2:1.13.1-96.gitb2f74b2.el7.centos will be installed
--> Processing Dependency: docker-common = 2:1.13.1-96.gitb2f74b2.el7.centos for package: 2:docker-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: docker-client = 2:1.13.1-96.gitb2f74b2.el7.centos for package: 2:docker-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: subscription-manager-rhsm-certificates for package: 2:docker-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Running transaction check
---> Package docker-client.x86_64 2:1.13.1-96.gitb2f74b2.el7.centos will be installed
---> Package docker-common.x86_64 2:1.13.1-96.gitb2f74b2.el7.centos will be installed
--> Processing Dependency: skopeo-containers >= 1:0.1.26-2 for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: oci-umount >= 2:2.3.3-3 for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: oci-systemd-hook >= 1:0.1.4-9 for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: oci-register-machine >= 1:0-5.13 for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: lvm2 >= 2.02.112 for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: container-storage-setup >= 0.9.0-1 for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: container-selinux >= 2:2.51-1 for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
--> Processing Dependency: atomic-registries for package: 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64
---> Package subscription-manager-rhsm-certificates.x86_64 0:1.21.10-3.el7.centos will be installed
--> Running transaction check
---> Package atomic-registries.x86_64 1:1.22.1-26.gitb507039.el7.centos will be installed
--> Processing Dependency: python-pytoml for package: 1:atomic-registries-1.22.1-26.gitb507039.el7.centos.x86_64
---> Package container-selinux.noarch 2:2.95-2.el7_6 will be installed
---> Package container-storage-setup.noarch 0:0.11.0-2.git5eaf76c.el7 will be installed
---> Package containers-common.x86_64 1:0.1.35-2.git404c5bd.el7.centos will be installed
---> Package lvm2.x86_64 7:2.02.180-10.el7_6.7 will be installed
--> Processing Dependency: lvm2-libs = 7:2.02.180-10.el7_6.7 for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: device-mapper-persistent-data >= 0.7.0-0.1.rc6 for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: liblvm2app.so.2.2(Base)(64bit) for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: libdevmapper-event.so.1.02(Base)(64bit) for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.4)(64bit) for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.1)(64bit) for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: liblvm2app.so.2.2()(64bit) for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: libdevmapper-event.so.1.02()(64bit) for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
--> Processing Dependency: libaio.so.1()(64bit) for package: 7:lvm2-2.02.180-10.el7_6.7.x86_64
---> Package oci-register-machine.x86_64 1:0-6.git2b44233.el7 will be installed
---> Package oci-systemd-hook.x86_64 1:0.1.18-3.git8787307.el7_6 will be installed
--> Processing Dependency: libyajl.so.2()(64bit) for package: 1:oci-systemd-hook-0.1.18-3.git8787307.el7_6.x86_64
---> Package oci-umount.x86_64 2:2.3.4-2.git87f9237.el7 will be installed
--> Running transaction check
---> Package device-mapper-event-libs.x86_64 7:1.02.149-10.el7_6.7 will be installed
---> Package device-mapper-persistent-data.x86_64 0:0.7.3-3.el7 will be installed
---> Package libaio.x86_64 0:0.3.109-13.el7 will be installed
---> Package lvm2-libs.x86_64 7:2.02.180-10.el7_6.7 will be installed
--> Processing Dependency: device-mapper-event = 7:1.02.149-10.el7_6.7 for package: 7:lvm2-libs-2.02.180-10.el7_6.7.x86_64
---> Package python-pytoml.noarch 0:0.1.14-1.git7dea353.el7 will be installed
---> Package yajl.x86_64 0:2.0.4-4.el7 will be installed
--> Running transaction check
---> Package device-mapper-event.x86_64 7:1.02.149-10.el7_6.7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

=============================================================================================
 Package                              Arch   Version                           Repository
                                                                                        Size
=============================================================================================
Installing:
 docker                               x86_64 2:1.13.1-96.gitb2f74b2.el7.centos extras   18 M
Installing for dependencies:
 atomic-registries                    x86_64 1:1.22.1-26.gitb507039.el7.centos extras   35 k
 container-selinux                    noarch 2:2.95-2.el7_6                    extras   39 k
 container-storage-setup              noarch 0.11.0-2.git5eaf76c.el7           extras   35 k
 containers-common                    x86_64 1:0.1.35-2.git404c5bd.el7.centos  extras   21 k
 device-mapper-event                  x86_64 7:1.02.149-10.el7_6.7             updates 189 k
 device-mapper-event-libs             x86_64 7:1.02.149-10.el7_6.7             updates 188 k
 device-mapper-persistent-data        x86_64 0.7.3-3.el7                       base    405 k
 docker-client                        x86_64 2:1.13.1-96.gitb2f74b2.el7.centos extras  3.9 M
 docker-common                        x86_64 2:1.13.1-96.gitb2f74b2.el7.centos extras   96 k
 libaio                               x86_64 0.3.109-13.el7                    base     24 k
 lvm2                                 x86_64 7:2.02.180-10.el7_6.7             updates 1.3 M
 lvm2-libs                            x86_64 7:2.02.180-10.el7_6.7             updates 1.1 M
 oci-register-machine                 x86_64 1:0-6.git2b44233.el7              extras  1.1 M
 oci-systemd-hook                     x86_64 1:0.1.18-3.git8787307.el7_6       extras   34 k
 oci-umount                           x86_64 2:2.3.4-2.git87f9237.el7          extras   32 k
 python-pytoml                        noarch 0.1.14-1.git7dea353.el7           extras   18 k
 subscription-manager-rhsm-certificates
                                      x86_64 1.21.10-3.el7.centos              updates 207 k
 yajl                                 x86_64 2.0.4-4.el7                       base     39 k

Transaction Summary
=============================================================================================
Install  1 Package (+18 Dependent packages)

Total download size: 26 M
Installed size: 89 M
Downloading packages:
(1/19): container-storage-setup-0.11.0-2.git5eaf76c.el7.noarch.rpm    |  35 kB  00:00:00
(2/19): atomic-registries-1.22.1-26.gitb507039.el7.centos.x86_64.rpm  |  35 kB  00:00:00
(3/19): container-selinux-2.95-2.el7_6.noarch.rpm                     |  39 kB  00:00:00
(4/19): containers-common-0.1.35-2.git404c5bd.el7.centos.x86_64.rpm   |  21 kB  00:00:00
(5/19): device-mapper-persistent-data-0.7.3-3.el7.x86_64.rpm          | 405 kB  00:00:00
(6/19): docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64.rpm      |  96 kB  00:00:00
(7/19): libaio-0.3.109-13.el7.x86_64.rpm                              |  24 kB  00:00:00
(8/19): device-mapper-event-1.02.149-10.el7_6.7.x86_64.rpm            | 189 kB  00:00:00
(9/19): device-mapper-event-libs-1.02.149-10.el7_6.7.x86_64.rpm       | 188 kB  00:00:00
(10/19): docker-client-1.13.1-96.gitb2f74b2.el7.centos.x86_64.rpm     | 3.9 MB  00:00:00
(11/19): lvm2-2.02.180-10.el7_6.7.x86_64.rpm                          | 1.3 MB  00:00:00
(12/19): oci-systemd-hook-0.1.18-3.git8787307.el7_6.x86_64.rpm        |  34 kB  00:00:00
(13/19): lvm2-libs-2.02.180-10.el7_6.7.x86_64.rpm                     | 1.1 MB  00:00:00
(14/19): oci-register-machine-0-6.git2b44233.el7.x86_64.rpm           | 1.1 MB  00:00:00
(15/19): python-pytoml-0.1.14-1.git7dea353.el7.noarch.rpm             |  18 kB  00:00:00
(16/19): oci-umount-2.3.4-2.git87f9237.el7.x86_64.rpm                 |  32 kB  00:00:00
(17/19): yajl-2.0.4-4.el7.x86_64.rpm                                  |  39 kB  00:00:00
(18/19): subscription-manager-rhsm-certificates-1.21.10-3.el7.centos. | 207 kB  00:00:00
(19/19): docker-1.13.1-96.gitb2f74b2.el7.centos.x86_64.rpm            |  18 MB  00:00:00
---------------------------------------------------------------------------------------------
Total                                                         24 MB/s |  26 MB  00:00:01
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : libaio-0.3.109-13.el7.x86_64                                             1/19
  Installing : 7:device-mapper-event-libs-1.02.149-10.el7_6.7.x86_64                    2/19
  Installing : yajl-2.0.4-4.el7.x86_64                                                  3/19
  Installing : 2:oci-umount-2.3.4-2.git87f9237.el7.x86_64                               4/19
  Installing : 1:oci-systemd-hook-0.1.18-3.git8787307.el7_6.x86_64                      5/19
  Installing : 7:device-mapper-event-1.02.149-10.el7_6.7.x86_64                         6/19
  Installing : 7:lvm2-libs-2.02.180-10.el7_6.7.x86_64                                   7/19
  Installing : device-mapper-persistent-data-0.7.3-3.el7.x86_64                         8/19
  Installing : 7:lvm2-2.02.180-10.el7_6.7.x86_64                                        9/19
  Installing : container-storage-setup-0.11.0-2.git5eaf76c.el7.noarch                  10/19
  Installing : subscription-manager-rhsm-certificates-1.21.10-3.el7.centos.x86_64      11/19
  Installing : 1:containers-common-0.1.35-2.git404c5bd.el7.centos.x86_64               12/19
  Installing : 1:oci-register-machine-0-6.git2b44233.el7.x86_64                        13/19
  Installing : python-pytoml-0.1.14-1.git7dea353.el7.noarch                            14/19
  Installing : 1:atomic-registries-1.22.1-26.gitb507039.el7.centos.x86_64              15/19
  Installing : 2:container-selinux-2.95-2.el7_6.noarch                                 16/19
  Installing : 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64                  17/19
  Installing : 2:docker-client-1.13.1-96.gitb2f74b2.el7.centos.x86_64                  18/19
useradd: failed to reset the lastlog entry of UID 996: Permission denied
  Installing : 2:docker-1.13.1-96.gitb2f74b2.el7.centos.x86_64                         19/19
  Verifying  : 2:container-selinux-2.95-2.el7_6.noarch                                  1/19
  Verifying  : 2:oci-umount-2.3.4-2.git87f9237.el7.x86_64                               2/19
  Verifying  : 7:lvm2-libs-2.02.180-10.el7_6.7.x86_64                                   3/19
  Verifying  : python-pytoml-0.1.14-1.git7dea353.el7.noarch                             4/19
  Verifying  : 2:docker-1.13.1-96.gitb2f74b2.el7.centos.x86_64                          5/19
  Verifying  : device-mapper-persistent-data-0.7.3-3.el7.x86_64                         6/19
  Verifying  : 2:docker-client-1.13.1-96.gitb2f74b2.el7.centos.x86_64                   7/19
  Verifying  : yajl-2.0.4-4.el7.x86_64                                                  8/19
  Verifying  : 7:device-mapper-event-libs-1.02.149-10.el7_6.7.x86_64                    9/19
  Verifying  : 1:oci-register-machine-0-6.git2b44233.el7.x86_64                        10/19
  Verifying  : 7:device-mapper-event-1.02.149-10.el7_6.7.x86_64                        11/19
  Verifying  : container-storage-setup-0.11.0-2.git5eaf76c.el7.noarch                  12/19
  Verifying  : 2:docker-common-1.13.1-96.gitb2f74b2.el7.centos.x86_64                  13/19
  Verifying  : 1:containers-common-0.1.35-2.git404c5bd.el7.centos.x86_64               14/19
  Verifying  : 7:lvm2-2.02.180-10.el7_6.7.x86_64                                       15/19
  Verifying  : 1:atomic-registries-1.22.1-26.gitb507039.el7.centos.x86_64              16/19
  Verifying  : libaio-0.3.109-13.el7.x86_64                                            17/19
  Verifying  : subscription-manager-rhsm-certificates-1.21.10-3.el7.centos.x86_64      18/19
  Verifying  : 1:oci-systemd-hook-0.1.18-3.git8787307.el7_6.x86_64                     19/19

Installed:
  docker.x86_64 2:1.13.1-96.gitb2f74b2.el7.centos

Dependency Installed:
  atomic-registries.x86_64 1:1.22.1-26.gitb507039.el7.centos
  container-selinux.noarch 2:2.95-2.el7_6
  container-storage-setup.noarch 0:0.11.0-2.git5eaf76c.el7
  containers-common.x86_64 1:0.1.35-2.git404c5bd.el7.centos
  device-mapper-event.x86_64 7:1.02.149-10.el7_6.7
  device-mapper-event-libs.x86_64 7:1.02.149-10.el7_6.7
  device-mapper-persistent-data.x86_64 0:0.7.3-3.el7
  docker-client.x86_64 2:1.13.1-96.gitb2f74b2.el7.centos
  docker-common.x86_64 2:1.13.1-96.gitb2f74b2.el7.centos
  libaio.x86_64 0:0.3.109-13.el7
  lvm2.x86_64 7:2.02.180-10.el7_6.7
  lvm2-libs.x86_64 7:2.02.180-10.el7_6.7
  oci-register-machine.x86_64 1:0-6.git2b44233.el7
  oci-systemd-hook.x86_64 1:0.1.18-3.git8787307.el7_6
  oci-umount.x86_64 2:2.3.4-2.git87f9237.el7
  python-pytoml.noarch 0:0.1.14-1.git7dea353.el7
  subscription-manager-rhsm-certificates.x86_64 0:1.21.10-3.el7.centos
  yajl.x86_64 0:2.0.4-4.el7

Complete!
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
