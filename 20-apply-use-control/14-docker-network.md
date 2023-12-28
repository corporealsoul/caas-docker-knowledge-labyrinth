### Docker Network,

**On host machine, ifconfig**

    docker0: Interface
    inet 172.17.0.1, defaut gateway
    inet 172.17.0.1  netmask 255.255.0.0  broadcast 172.17.255.255
    inet addr:172.17.0.2


### Create Network,

`anup@ubuntu-22042-08:~$ docker network ls`

`anup@ubuntu-22042-08:~$ docker network create docker-network`

`anup@ubuntu-22042-08:~$ docker network create --driver bridge network-name`

`anup@ubuntu-22042-08:~$ docker network ls`

`anup@ubuntu-22042-08:~$ docker network inspect docker-network`

`anup@ubuntu-22042-08:~$ docker network inspect network-name`

`anup@ubuntu-22042-08:~$ docker info | grep -i "network"`


### Spin up a container,

`anup@ubuntu-22042-08:~$ docker images`

`anup@ubuntu-22042-08:~$ docker run --network=network-name -itd --name=container-name busybox`

`anup@ubuntu-22042-08:~$ docker network inspect network-name`

`anup@ubuntu-22042-08:~$ docker network inspect network-name | grep -i "e9a972ae39e32709b7db3f6d1d686493f80a3662f232895acb15520dc1733d80"`

or,

`anup@ubuntu-22042-08:~$ docker network connect network-name container-name`

`anup@ubuntu-22042-08:~$ docker network disconnect networkname container-name`


### Port mapping,

`anup@ubuntu-22042-08:~$ docker image pull nginx`

`anup@ubuntu-22042-08:~$ docker run -d -p 80:80 nginx `

<br>
