### Docker volume (Share Between Containers),

**Docker volume using Dockerfile,**

`anup@ubuntu-22042-08:~$ nano Dockerfile `

    FROM ubuntu
    VOLUME ["shared-volume"]

`anup@ubuntu-22042-08:~$ docker build -t shared-volume-image .`

`anup@ubuntu-22042-08:~$ docker images`

`anup@ubuntu-22042-08:~$ docker run -it --name shared-volume-container shared-volume-image /bin/bash`

`root@0aa923ebba4e:/# ls -ltr`

`root@77a875eac05b:/# cd shared-volume/`

<br>

`anup@ubuntu-22042-08:~$ docker run -it --name shared-volume-second-container  --privileged=true --volumes-from shared-volume-container ubuntu /bin/bash`

`root@adf8f88c5ee0:/# ls -ltr`

`root@0aa923ebba4e:/# cd shared-volume/`

`root@77a875eac05b:/shared-volume# touch a-file`


**Docker volume without using Dockerfile,**

`anup@ubuntu-22042-08:~$ docker run -it --name shared-volume-container -v /shared-volume ubuntu /bin/bash`

`root@5bb08b6f3f47:/# ls -ltr`

`root@5bb08b6f3f47:/# cd shared-volume/`

<br>

`anup@ubuntu-22042-08:~$ docker run -it --name shared-volume-second-container --privileged=true --volumes-from shared-volume-container ubuntu /bin/bash`

`root@0f0255aff33e:/# ls -ltr`

`root@0f0255aff33e:/# cd shared-volume/`

`root@0f0255aff33e:/shared-volume# touch a-file `


### Docker volume (Share Between Host and Container),

`anup@ubuntu-22042-08:~$ docker run -t -d -P -v /tmp/nginx/html:/usr/share/nginx/html --name nginxcont nginx:latest`

`anup@ubuntu-22042-08:~$ docker run -it -d -p 80:80 -v /home/anup/nginx/html/:/usr/share/nginx/html nginx`

`anup@ubuntu-22042-08:~$ docker images`

`anup@ubuntu-22042-08:~$ docker ps`

`anup@ubuntu-22042-08:~$ docker exec -it b5652e0d1b2c /bin/bash`

`root@b5652e0d1b2c:/# ls -ltr /usr/share/nginx/html/`

<br>

`anup@ubuntu-22042-08:~$ sudo touch /tmp/nginx/html/a-file`

<br>
