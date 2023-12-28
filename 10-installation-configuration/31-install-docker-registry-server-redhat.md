
### Registry Server,

https://docs.docker.com/registry/deploying/

`[anup@rhel-92-04 ~]$ docker version`

`[anup@rhel-92-04 ~]$ docker --version`

`[anup@rhel-92-04 ~]$ docker compose version`

<br>

### Installation,

`[anup@rhel-92-04 ~]$ docker run -d -p 5000:5000 --restart=always --name registry registry:2`

`[anup@rhel-92-04 ~]$ docker images`

`[anup@rhel-92-04 ~]$ docker ps `

<br>

### Copy an image from Docker Hub to your registry,

**Pull the ubuntu:16.04 image from Docker Hub.**

`[anup@rhel-92-04 ~]$ docker pull ubuntu:16.04`

`[anup@rhel-92-04 ~]$ dokcer images`

<br>

**Tag the image as localhost:5000/my-ubuntu. This creates an additional tag for the existing image. When the first part of the tag is a hostname and port, Docker interprets this as the location of a registry, when pushing.**

`[anup@rhel-92-04 ~]$ docker tag ubuntu:16.04 localhost:5000/my-ubuntu`

`[anup@rhel-92-04 ~]$ docker images`

<br>

**Push the image to the local registry running at localhost:5000**

`[anup@rhel-92-04 ~]$ docker push localhost:5000/my-ubuntu:latest`

<br>

**Remove the locally-cached ubuntu:16.04 and localhost:5000/my-ubuntu images, so that you can test pulling the image from your registry. This does not remove the localhost:5000/my-ubuntu image from your registry.**

`[anup@rhel-92-04 ~]$ docker image remove ubuntu:16.04`

`[anup@rhel-92-04 ~]$ docker image remove localhost:5000/my-ubuntu`

<br>

`[anup@rhel-92-04 ~]$ docker pull localhost:5000/my-ubuntu`

`[anup@rhel-92-04 ~]$ docker images`

<br>

`[anup@rhel-92-04 ~]$ docker pull localhost:5000/my-ubuntu`

`[anup@rhel-92-04 ~]$ docker images`

<br>

### Control a local registry,

`[anup@rhel-92-04 ~]$ docker container stop registry`

`[anup@rhel-92-04 ~]$ docker container start registry`

<br>
