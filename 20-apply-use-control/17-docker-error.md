### Docker error analysis,

`anup@ubuntu-22042-08:~$ docker run -it -d -p 80:80 -v /home/anup/nginx/html/:/usr/share/nginx/html nginx`

`anup@ubuntu-22042-08:~$ docker ps`

`anup@ubuntu-22042-08:~$ docker export eafaff02886e > export.tar`

`anup@ubuntu-22042-08:~$ ls -ltr`

`anup@ubuntu-22042-08:~$ docker import - alpineimage < export.ta`

`anup@ubuntu-22042-08:~$ docker ps`

<br>
