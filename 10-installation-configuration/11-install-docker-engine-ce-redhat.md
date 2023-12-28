## Install Docker Engine on Red Hat,

https://docs.docker.com/engine/install/rhel/

### Uninstall old versions,

    [anup@rhel-92-04 ~]$ sudo yum remove docker \
                      docker-client \
                      docker-client-latest \
                      docker-common \
                      docker-latest \
                      docker-latest-logrotate \
                      docker-logrotate \
                      docker-engine \
                      podman \
                      runc


### Install using the rpm repository,

**Set up the repository,**

    [anup@rhel-92-04 ~]$ sudo yum update
    
    [anup@rhel-92-04 ~]$ sudo yum install -y yum-utils
    
    [anup@rhel-92-04 ~]$ sudo yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
    
    [anup@rhel-92-04 ~]$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

**Install Docker Engine,**

    [anup@rhel-92-04 ~]$ sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

<br>

    [anup@rhel-92-04 ~]$ docker --version
    
    [anup@rhel-92-04 ~]$ sudo systemctl status docker.service 
    
    [anup@rhel-92-04 ~]$ sudo systemctl start docker.service
    
    [anup@rhel-92-04 ~]$ sudo systemctl enable docker.service 
    
    [anup@rhel-92-04 ~]$ sudo docker run hello-world


### Manage Docker as a non-root user,

    [anup@rhel-92-04 ~]$ sudo groupadd docker
    
    [anup@rhel-92-04 ~]$ sudo usermod -aG docker $USER
    
    [anup@rhel-92-04 ~]$ newgrp docker
    
    [anup@rhel-92-04 ~]$ docker run hello-world

<br>
