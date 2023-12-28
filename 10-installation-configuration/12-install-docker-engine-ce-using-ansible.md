`[anup@rhel-92-104 ~]$ ansible -m ping all`

`[anup@rhel-92-104 playbook]$ ansible-inventory --list`

<br>

`[anup@rhel-92-104 ~]$ cd /etc/ansible/roles`

`[anup@rhel-92-104 roles]$ sudo ansible-galaxy init docker-installation-ubuntu`

<br>

`[anup@rhel-92-104 ~]$ cd /etc/ansible/playbook/`

`[anup@rhel-92-104 playbook]$ ansible-playbook docker-installation-ubuntu-site.yml --syntax-check`

`[anup@rhel-92-104 playbook]$ ansible-playbook docker-installation-ubuntu-site.yml --ask-become-pass`


<br>

`anup@ubuntu-22042-108:~$ docker --version`
