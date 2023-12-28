### Docker UCP,

https://hub.docker.com/r/docker/ucp

`[anup@rhel-92-04 ~]$ docker image pull docker/ucp`

`[anup@rhel-92-04 ~]$ docker images`


    docker run --rm -it \
      --name ucp \
      -v /var/run/docker.sock:/var/run/docker.sock \
      docker/ucp \
      --help

<br>

    docker container run --rm -it --name ucp \
      -v /var/run/docker.sock:/var/run/docker.sock \
      docker/ucp:2.2.6 install \
      --host-address 192.168.56.8 \
      --interactive

<br>

    docker container run --rm -it --name ucp \
      -v /var/run/docker.sock:/var/run/docker.sock \
      docker/ucp install \
      --host-address 192.168.56.8 \
      --unmanaged-cni \
      --interactive

### Mirantis UCP,

https://docs.mirantis.com/mke/3.5/release-notes.html

    docker container run --rm -it --name ucp \
      -v /var/run/docker.sock:/var/run/docker.sock \
      mirantis/ucp:3.5.9 install \
      --host-address 192.168.56.8 \
      --unmanaged-cni \
      --interactive

<br>

    Admin Username: admin
    Admin Password: 1$a85W$0xTMhq
    Confirm Admin Password: 1$a85W$0xTMhq


https://192.168.56.8

https://192.168.56.8/ca

<br>
