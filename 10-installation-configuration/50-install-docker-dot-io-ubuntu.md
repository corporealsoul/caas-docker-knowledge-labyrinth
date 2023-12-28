### Install docker.io on Ubuntu,


`anup@ubuntu-22042-08:~$ sudo apt-cache search ^docker`

`anup@ubuntu-22042-08:~$ sudo apt-cache search ^docker | grep -i "docker.io"`



**Note :** docker-ce is provided by docker.com, docker.io is provided by Debian.

**https://www.docker.com/**

**https://salsa.debian.org/go-team/packages/docker/-/blob/master/debian/control**

<br>

### Installation,

`anup@ubuntu-22042-08:~$ sudo apt-get install docker.io docker-compose -y`

`anup@ubuntu-22042-08:~$ docker --version`

`anup@ubuntu-22042-08:~$ sudo systemctl status docker.service `

`anup@ubuntu-22042-08:~$ sudo systemctl start docker.service `

<br>

