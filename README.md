### basicdocker

https://docs.docker.com/engine/install/ubuntu/

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Downloads

$ ssh -i ubuntu-vm_key.pem azureuser@20.124.104.28

The authenticity of host '20.124.104.28 (20.124.104.28)' can't be established.

ECDSA key fingerprint is SHA256:e4P9GWDUkeU  

Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

Warning: Permanently added '20.124.104.28' (ECDSA) to the list of known hosts.

Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.11.0-1021-azure x86_64)

 * Documentation:  https://help.ubuntu.com

* Management:     https://landscape.canonical.com

* Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 19 02:10:21 UTC 2021

  System load:  0.0               Processes:             127      

Usage of /:   4.6% of 28.90GB   Users logged in:       0        

Memory usage: 3%                IPv4 address for eth0: 10.0.0.4 

Swap usage:   0%

1 update can be applied immediately.

To see these additional updates run: apt list --upgradable


The list of available updates is more than a week old.

To check for new updates run: sudo apt update


The programs included with the Ubuntu system are free software; the exact distribution terms for each program are described in the


individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by applicable law.

To run a command as administrator (user "root"), use "sudo <command>".

See "man sudo_root" for details.

azureuser@ubuntu-vm:~$ hostnamectl

Static hostname: ubuntu-vm

Icon name: computer-vm

Chassis: vm

Machine ID: bc3fe1188f2c49a6bdacc7486d2f695d

Boot ID: 6f3637c5440c4767b637dc2bb405677d

Virtualization: microsoft

Operating System: Ubuntu 20.04.3 LTS

Kernel: Linux 5.11.0-1021-azure


Architecture: x86-64

azureuser@ubuntu-vm:~$  sudo apt-get remove docker docker-engine docker.io containerd runc

Reading package lists... Done

Building dependency tree

Reading state information... Done

Package 'docker.io' is not installed, so not removed

E: Unable to locate package docker


E: Unable to locate package docker-engine

azureuser@ubuntu-vm:~$ sudo apt-get update

Hit:1 http://azure.archive.ubuntu.com/ubuntu focal InRelease
   
Get:10 http://azure.archive.ubuntu.com/ubuntu focal/multiverse amd64 c-n-f Metadata [9136 B]

Fetched 20.6 MB in 3s (6515 kB/s)

Reading package lists... Done
azureuser@ubuntu-vm:~$

azureuser@ubuntu-vm:~$ sudo apt-get install \

>     ca-certificates \

>     curl \

>     gnupg \

>     lsb-release

Reading package lists... Done

Building dependency tree

Reading state information... Done

lsb-release is already the newest version (11.1.0ubuntu2).

lsb-release set to manually installed.

ca-certificates is already the newest version (20210119~20.04.2).

ca-certificates set to manually installed.

curl is already the newest version (7.68.0-1ubuntu2.7).

curl set to manually installed.

gnupg is already the newest version (2.2.19-3ubuntu2.1).

gnupg set to manually installed.

0 upgraded, 0 newly installed, 0 to remove and 24 not upgraded.

azureuser@ubuntu-vm:~$


azureuser@ubuntu-vm:~$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpgclient_loop: 

send disconnect: Connection reset by peer

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Downloads

$ ssh -i ubuntu-vm_key.pem azureuser@20.124.104.28

Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.11.0-1021-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 19 02:53:40 UTC 2021

  System load:  0.0               Processes:             127
  Usage of /:   5.1% of 28.90GB   Users logged in:       0
  Memory usage: 3%                IPv4 address for eth0: 10.0.0.4
  Swap usage:   0%


18 updates can be applied immediately.
11 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable


Last login: Fri Nov 19 02:16:35 2021 from 73.152.119.181

azureuser@ubuntu-vm:~$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

azureuser@ubuntu-vm:~$ echo \
>   "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
>   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
azureuser@ubuntu-vm:~$ sudo apt-get update
Hit:1 http://azure.archive.ubuntu.com/ubuntu focal InRelease
.
.
Fetched 184 kB in 0s (370 kB/s)
Reading package lists... Done
azureuser@ubuntu-vm:~$ 
azureuser@ubuntu-vm:~$ 
azureuser@ubuntu-vm:~$ 
azureuser@ubuntu-vm:~$ sudo apt-get install docker-ce docker-ce-cli containerd.io
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  docker-ce-rootless-extras docker-scan-plugin pigz slirp4netns

Processing triggers for systemd (245.4-4ubuntu3.13) ...
azureuser@ubuntu-vm:~$ docker run hello-world
docker: Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create": dial unix /var/run/docker.sock: connect: permission denied.
See 'docker run --help'.
azureuser@ubuntu-vm:~$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:cc15c5b292d8525effc0f89cb299f1804f3a725c8d05e158653a563f15e4f685
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:

1. The Docker client contacted the Docker daemon.

2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)

3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.

4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:

$ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:  https://hub.docker.com/

For more examples and ideas, visit:

https://docs.docker.com/get-started/

azureuser@ubuntu-vm:~$ 
azureuser@ubuntu-vm:~$ 
azureuser@ubuntu-vm:~$ 

azureuser@ubuntu-vm:~$ sudo groupadd docker

groupadd: group 'docker' already exists

azureuser@ubuntu-vm:~$ sudo usermod -aG docker $USER

azureuser@ubuntu-vm:~$ logout

Connection to 20.124.104.28 closed.

oeume@KRISOLIZ-SFFHPDPC MINGW64 ~/Downloads

$ ssh -i ubuntu-vm_key.pem azureuser@20.124.104.28

Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.11.0-1021-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Nov 19 03:09:36 UTC 2021

  System load:  0.0               Processes:                128
  Usage of /:   6.7% of 28.90GB   Users logged in:          0
  Memory usage: 4%                IPv4 address for docker0: 172.17.0.1
  Swap usage:   0%                IPv4 address for eth0:    10.0.0.4


18 updates can be applied immediately.

11 of these updates are standard security updates.

To see these additional updates run: apt list --upgradable


Last login: Fri Nov 19 02:53:40 2021 from 73.152.119.181
azureuser@ubuntu-vm:~$ docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
