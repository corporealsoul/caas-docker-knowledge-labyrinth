### Docker Trusted Registry

https://hub.docker.com/r/docker/dtr

`[anup@rhel-92-04 ~]$ docker run -it --rm docker/dtr install --ucp-insecure-tls`

`[anup@rhel-92-04 ~]$ docker run -it --rm docker/dtr:2.4.12 install --ucp-insecure-tls`

`[anup@rhel-92-04 ~]$ docker run -it --rm docker/dtr join --ucp-node ubuntu-22042-08 --ucp-insecure-tls`

<br>

    docker run -it --rm \
    docker/dtr install \
    --ucp-url https://192.168.56.8 \
    --ucp-node ubuntu-22042-08 \
    --dtr-external-url https://192.168.56.4 \
    --ucp-username admin --ucp-password 1$a85W$0xTMhq

<br>

**Note :** Make sure that the node you install DTR on is already joined to the UCP cluster.

    ucp-url (The UCP URL including domain and port): https://192.168.56.8:8443
    ucp-username (The UCP administrator username): admin
    ucp-password: 1$a85W$0xTMhq

<br>

**Error :** FATA[0033] Failed to choose ucp node: The UCP cluster does not have any available nodes without conflicting with ports '[80, 443]' 

**Error :** FATA[0071] Failed to get new conv client: failed to create http client: Failed to get UCP CA: Get https://192.168.56.8:8443/ca: dial tcp 192.168.56.8:8443: connect: connection refused 

<br>
