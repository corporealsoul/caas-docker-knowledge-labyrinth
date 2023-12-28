### Install,

https://docs.docker.com/engine/install/

`[anup@c7-80-docker ~]$ docker version`

`[anup@c7-80-docker ~]$ docker --version`

`[anup@c7-80-docker ~]$ docker info` 

### Important directory and Control Docker,

`root@u20-80-docker:~# cd /var/lib/docker` 

<br>

`[anup@c7-80-docker ~]$ sudo systemctl status docker.service `

`[anup@c7-80-docker ~]$ sudo systemctl start docker.service ` 


### Image to container,

    docker create nginx
    docker start -a 28edd0898859
    docker start
    docker attach (-a)
    docker run , (create+start)
    docker exec -i -t 60da1cdc8568 sh

`anup@ubuntu-22042-08:~$ docker pull nginx`

`anup@ubuntu-22042-08:~$ docker create nginx`

`anup@ubuntu-22042-08:~$ docker images`

`anup@ubuntu-22042-08:~$ docker ps -a`

`anup@ubuntu-22042-08:~$ docker start -a 28edd089885921591dc40b90a1f746375bd5203cb9ffa032eb83909098fb8798`

`anup@ubuntu-22042-08:~$ docker exec -it 28edd0898859 /bin/bash`

`anup@ubuntu-22042-08:~$ docker diff 28edd0898859`

`anup@ubuntu-22042-08:~$ docker logs 28edd0898859`

`anup@ubuntu-22042-08:~$ docker stop 28edd0898859`

<br>

`anup@ubuntu-22042-08:~$ docker run -it --name nginx-container nginx /bin/bash`

`anup@ubuntu-22042-08:~$ docker images`

`anup@ubuntu-22042-08:~$ docker ps -a`

### Container to images,

`anup@ubuntu-22042-08:~$ docker commit nginx-container nginx-image`

`anup@ubuntu-22042-08:~$ docker images`

<br>
