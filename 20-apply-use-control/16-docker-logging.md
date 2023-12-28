### Docker logging,

`anup@ubuntu-22042-08:~$ docker info | grep 'Logging Driver'`

`anup@ubuntu-22042-08:~$ cd /etc/docker/`

`anup@ubuntu-22042-08:/etc/docker$ docker run -it -d -p 80:80 -v /home/anup/nginx/html/:/usr/share/nginx/html nginx`

`anup@ubuntu-22042-08:/etc/docker$ docker ps`

`anup@ubuntu-22042-08:/etc/docker$ docker logs eafaff02886e`

<br>
