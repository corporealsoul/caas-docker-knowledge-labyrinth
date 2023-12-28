### Docker file,

`anup@ubuntu-22042-08:~$ touch copied `

`anup@ubuntu-22042-08:~$ nano copied `

`anup@ubuntu-22042-08:~$ nano Dockerfile`

    FROM ubuntu
    WORKDIR /tmp
    RUN echo "Realm Regal." > /tmp/echoed
    ENV user anup
    COPY copied /tmp

`anup@ubuntu-22042-08:~$ docker build -t dockerfile-image .`

`anup@ubuntu-22042-08:~$ docker images`

`anup@ubuntu-22042-08:~$ docker run -it --name docker-container dockerfile-image /bin/bash`

`root@efcc13976c3c:/tmp# ls -ltr`

`root@efcc13976c3c:/tmp# cat copied `

`root@efcc13976c3c:/tmp# cat echoed `

<br>
