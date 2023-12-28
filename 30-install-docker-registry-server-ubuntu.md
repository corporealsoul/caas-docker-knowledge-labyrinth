### Registry Server,

https://docs.docker.com/registry/deploying/

`anup@ubuntu-22042-08:~$ docker version`

`anup@ubuntu-22042-08:~$ docker --version`

`anup@ubuntu-22042-08:~$ docker compose version`

<br>

### Installing and Configuring the Docker Registry,

`anup@ubuntu-22042-08:~$ mkdir ~/docker-registry`

`anup@ubuntu-22042-08:~$ cd ~/docker-registry`

`anup@ubuntu-22042-08:~/docker-registry$ mkdir data`

`anup@ubuntu-22042-08:~/docker-registry$ nano docker-compose.yml`

    version: '3'
    
    services:
      registry:
        image: registry:2
        ports:
        - "5000:5000"
        environment:
          REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY: /data
        volumes:
          - ./data:/data

`anup@ubuntu-22042-08:~/docker-registry$ docker compose up`

`anup@ubuntu-22042-08:~/docker-registry$ docker compose up -d`

<br>

`anup@ubuntu-22042-08:~/docker-registry$ docker images`

`anup@ubuntu-22042-08:~/docker-registry$ docker ps`

<br>

**Pull the ubuntu:16.04 image from Docker Hub.**

`anup@ubuntu-22042-08:~/docker-registry$ docker pull ubuntu:16.04`

`anup@ubuntu-22042-08:~/docker-registry$ dokcer images`

<br>

**Tag the image as localhost:5000/my-ubuntu. This creates an additional tag for the existing image. When the first part of the tag is a hostname and port, Docker interprets this as the location of a registry, when pushing.**

`anup@ubuntu-22042-08:~/docker-registry$ docker tag ubuntu:16.04 localhost:5000/my-ubuntu`

`anup@ubuntu-22042-08:~/docker-registry$ docker images`

<br>

**Push the image to the local registry running at localhost:5000**

`anup@ubuntu-22042-08:~/docker-registry$ docker push localhost:5000/my-ubuntu:latest`

<br>

**Remove the locally-cached ubuntu:16.04 and localhost:5000/my-ubuntu images, so that you can test pulling the image from your registry. This does not remove the localhost:5000/my-ubuntu image from your registry.**

`anup@ubuntu-22042-08:~/docker-registry$ docker image remove ubuntu:16.04`

`anup@ubuntu-22042-08:~/docker-registry$ docker image remove localhost:5000/my-ubuntu`

<br>

`anup@ubuntu-22042-08:~/docker-registry$ docker pull localhost:5000/my-ubuntu`

`anup@ubuntu-22042-08:~/docker-registry$ docker images`

<br>

`anup@ubuntu-22042-08:~/docker-registry$ docker compose down`

<br>
