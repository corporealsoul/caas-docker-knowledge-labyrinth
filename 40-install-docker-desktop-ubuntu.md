### Install Docker Desktop on Ubuntu,

**https://docs.docker.com/desktop/install/linux-install/**

**https://docs.docker.com/desktop/install/ubuntu/**

### Download latest DEB package,

`anup@ubuntu-22042-08:~$ wget https://desktop.docker.com/linux/main/amd64/docker-desktop-4.21.0-amd64.deb`

`anup@ubuntu-22042-08:~$ ls -ltr`

`anup@ubuntu-22042-08:~$ sudo apt-get update`

`anup@ubuntu-22042-08:~$ sudo apt-get install ./docker-desktop-<version>-<arch>.deb`

`anup@ubuntu-22042-08:~$ sudo apt-get install ./docker-desktop-4.21.0-amd64.deb`

<br>

### Control,

`anup@ubuntu-22042-08:~$ docker compose version`
 
`anup@ubuntu-22042-08:~$ docker --version`
 
`anup@ubuntu-22042-08:~$ docker version`
 
`anup@ubuntu-22042-08:~$ systemctl --user start docker-desktop`

`anup@ubuntu-22042-08:~$ systemctl --user enable docker-desktop`

<br>
