### basicdocker



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


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

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
Get:2 http://azure.archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]  
Get:3 http://azure.archive.ubuntu.com/ubuntu focal-backports InRelease [101 kB]
Get:4 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]      
Get:5 http://azure.archive.ubuntu.com/ubuntu focal/universe amd64 Packages [8628 kB]
Get:6 http://azure.archive.ubuntu.com/ubuntu focal/universe Translation-en [5124 kB]
Get:7 http://azure.archive.ubuntu.com/ubuntu focal/universe amd64 c-n-f Metadata [265 kB]
Get:8 http://azure.archive.ubuntu.com/ubuntu focal/multiverse amd64 Packages [144 kB]       
Get:9 http://azure.archive.ubuntu.com/ubuntu focal/multiverse Translation-en [104 kB]       
Get:10 http://azure.archive.ubuntu.com/ubuntu focal/multiverse amd64 c-n-f Metadata [9136 B]
Get:11 http://azure.archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [1344 kB]   
Get:12 http://azure.archive.ubuntu.com/ubuntu focal-updates/main Translation-en [276 kB]    
Get:13 http://azure.archive.ubuntu.com/ubuntu focal-updates/main amd64 c-n-f Metadata [14.5 kB]    
Get:14 http://azure.archive.ubuntu.com/ubuntu focal-updates/restricted amd64 Packages [569 kB]     
Get:15 http://azure.archive.ubuntu.com/ubuntu focal-updates/restricted Translation-en [81.6 kB]    
Get:16 http://azure.archive.ubuntu.com/ubuntu focal-updates/restricted amd64 c-n-f Metadata [528 B]
Get:17 http://azure.archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [876 kB]       
Get:18 http://azure.archive.ubuntu.com/ubuntu focal-updates/universe Translation-en [190 kB]
Get:19 http://azure.archive.ubuntu.com/ubuntu focal-updates/universe amd64 c-n-f Metadata [19.5 kB]
Get:20 http://azure.archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 Packages [24.5 kB]
Get:21 http://azure.archive.ubuntu.com/ubuntu focal-updates/multiverse Translation-en [6856 B]
Get:22 http://azure.archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 c-n-f Metadata [616 B]
Get:23 http://azure.archive.ubuntu.com/ubuntu focal-backports/main amd64 Packages [2568 B]
Get:24 http://azure.archive.ubuntu.com/ubuntu focal-backports/main Translation-en [1120 B]
Get:25 http://azure.archive.ubuntu.com/ubuntu focal-backports/main amd64 c-n-f Metadata [400 B]
Get:26 http://azure.archive.ubuntu.com/ubuntu focal-backports/restricted amd64 c-n-f Metadata [116 B]
Get:27 http://azure.archive.ubuntu.com/ubuntu focal-backports/universe amd64 Packages [6588 B]
Get:28 http://azure.archive.ubuntu.com/ubuntu focal-backports/universe Translation-en [3292 B]
Get:29 http://azure.archive.ubuntu.com/ubuntu focal-backports/universe amd64 c-n-f Metadata [580 B]
Get:30 http://azure.archive.ubuntu.com/ubuntu focal-backports/multiverse amd64 c-n-f Metadata [116 B]
Get:31 http://security.ubuntu.com/ubuntu focal-security/main amd64 Packages [987 kB]
Get:32 http://security.ubuntu.com/ubuntu focal-security/main Translation-en [184 kB]
Get:38 http://security.ubuntu.com/ubuntu focal-security/universe Trann-f Metadata [8880 B]slation-en [107 kB]                                                  d64 Packages [526 kB]
Get:39 http://security.ubuntu.com/ubuntu focal-security/universe amd64 c-n-f Metadata [12.9 kB]
Get:40 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 Packages [21.9 kB]
Get:41 http://security.ubuntu.com/ubuntu focal-security/multiverse Translation-en [4948 B]
Get:42 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 c-n-f Metadata [540 B]
Fetched 20.6 MB in 3s (6515 kB/s)
Reading package lists... Done
azureuser@ubuntu-vm:~$
azureuser@ubuntu-vm:~$
azureuser@ubuntu-vm:~$
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
azureuser@ubuntu-vm:~$
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
Hit:2 http://azure.archive.ubuntu.com/ubuntu focal-updates InRelease
Hit:3 http://azure.archive.ubuntu.com/ubuntu focal-backports InRelease
Get:4 https://download.docker.com/linux/ubuntu focal InRelease [57.7 kB]
Get:5 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Get:6 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages [12.9 kB]
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
Suggested packages:
  aufs-tools cgroupfs-mount | cgroup-lite
The following NEW packages will be installed:
  containerd.io docker-ce docker-ce-cli docker-ce-rootless-extras docker-scan-plugin pigz slirp4netns
0 upgraded, 7 newly installed, 0 to remove and 24 not upgraded.
Need to get 95.3 MB of archives.
After this operation, 402 MB of additional disk space will be used.
Do you want to continue? [Y/n] yes
Get:1 http://azure.archive.ubuntu.com/ubuntu focal/universe amd64 pigz amd64 2.4-1 [57.4 kB]
Get:2 http://azure.archive.ubuntu.com/ubuntu focal/universe amd64 slirp4netns amd64 0.4.3-1 [74.3 kB]
Get:3 https://download.docker.com/linux/ubuntu focal/stable amd64 containerd.io amd64 1.4.12-1 [23.7 MB]
Get:4 https://download.docker.com/linux/ubuntu focal/stable amd64 docker-ce-cli amd64 5:20.10.11~3-0~ubuntu-focal [38.8 MB]
Get:5 https://download.docker.com/linux/ubuntu focal/stable amd64 docker-ce amd64 5:20.10.11~3-0~ubuntu-focal [21.2 MB]
Get:6 https://download.docker.com/linux/ubuntu focal/stable amd64 docker-ce-rootless-extras amd64 5:20.10.11~3-0~ubuntu-focal [7920 kB]
Get:7 https://download.docker.com/linux/ubuntu focal/stable amd64 docker-scan-plugin amd64 0.9.0~ubuntu-focal [3518 kB]
Fetched 95.3 MB in 3s (30.4 MB/s)
Selecting previously unselected package pigz.
(Reading database ... 59731 files and directories currently installed.)
Preparing to unpack .../0-pigz_2.4-1_amd64.deb ...
Unpacking pigz (2.4-1) ...
Selecting previously unselected package containerd.io.
Preparing to unpack .../1-containerd.io_1.4.12-1_amd64.deb ...
Unpacking containerd.io (1.4.12-1) ...
Selecting previously unselected package docker-ce-cli.
Preparing to unpack .../2-docker-ce-cli_5%3a20.10.11~3-0~ubuntu-focal_amd64.deb ...
Unpacking docker-ce-cli (5:20.10.11~3-0~ubuntu-focal) ...
Selecting previously unselected package docker-ce.
Preparing to unpack .../3-docker-ce_5%3a20.10.11~3-0~ubuntu-focal_amd64.deb ...
Unpacking docker-ce (5:20.10.11~3-0~ubuntu-focal) ...
Selecting previously unselected package docker-ce-rootless-extras.
Preparing to unpack .../4-docker-ce-rootless-extras_5%3a20.10.11~3-0~ubuntu-focal_amd64.deb ...
Unpacking docker-ce-rootless-extras (5:20.10.11~3-0~ubuntu-focal) ...
Selecting previously unselected package docker-scan-plugin.
Preparing to unpack .../5-docker-scan-plugin_0.9.0~ubuntu-focal_amd64.deb ...
Unpacking docker-scan-plugin (0.9.0~ubuntu-focal) ...
Selecting previously unselected package slirp4netns.
Preparing to unpack .../6-slirp4netns_0.4.3-1_amd64.deb ...
Unpacking slirp4netns (0.4.3-1) ...
Setting up slirp4netns (0.4.3-1) ...
Setting up docker-scan-plugin (0.9.0~ubuntu-focal) ...
Setting up containerd.io (1.4.12-1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
Setting up docker-ce-cli (5:20.10.11~3-0~ubuntu-focal) ...
Setting up pigz (2.4-1) ...
Setting up docker-ce-rootless-extras (5:20.10.11~3-0~ubuntu-focal) ...
Setting up docker-ce (5:20.10.11~3-0~ubuntu-focal) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
Processing triggers for man-db (2.9.1-1) ...
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

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

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
