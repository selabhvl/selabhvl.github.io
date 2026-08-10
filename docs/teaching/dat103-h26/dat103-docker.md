# Small Linux installation with Alpine in Docker

Prompts: `%` = “outside” (use Linux, MacOS or Windows Powershell), `#` = administrator shell inside the container

## 1) Create basic container.

Note for Windows: use `${env:TMP}` instead of the `/tmp`.

```
% docker run -it --name dat103 --platform linux/amd64 -v /tmp:/app alpine:latest
```

Output:
```
Unable to find image 'alpine:latest' locally
latest: Pulling from library/alpine
55afa1ecc21d: Pull complete
Digest: sha256:28bd5fe8b56d1bd048e5babf5b10710ebe0bae67db86916198a6eec434943f8b
Status: Downloaded newer image for alpine:latest
/ #
```
The last line above is the system prompt, where the first component is the directory we are in at the moment, here the root `/`.

## 2) A quick look around, then exit:
```
/ # uname -a
Linux 9b6cbdd01dd1 6.12.76-linuxkit #1 SMP Mon Mar 30 09:10:35 UTC 2026 x86_64 Linux
/ # exit
%
```
Note that it’s “x86_64” even though you might now have an x86-based processor like the newer Apple Macs!

## 3) Reusing the container
```
% docker ps -a
CONTAINER ID   IMAGE                                                                                         COMMAND                  CREATED          STATUS                      PORTS                                                                                                                                 NAMES
9b6cbdd01dd1   alpine:latest   "/bin/sh"  40 seconds ago   Exited (0) 10 seconds ago
% docker restart dat103
dat103
% docker ps
CONTAINER ID   IMAGE           COMMAND     CREATED         STATUS         PORTS     NAMES
9b6cbdd01dd1   alpine:latest   "/bin/sh"   4 minutes ago   Up 3 seconds             dat103
% docker attach dat103
/ #
```

## 4) What did we do?
The `history` command shows which statements we had executed in the current/previous shell:
```
/ # history
   0 uname -a
   1 exit
   2 history
/ #
```
## 5) Let’s install some software and enable ssh

The error message related to `/sys/fs` doesn't matter for us here.
```
/ # apk add vim nasm build-base openrc openssh
… output …
/ # rc-status
 * Caching service dependencies ...
Service 'hwdrivers' needs non existent service 'dev'
Service 'machine-id' needs non existent service 'dev'                                                                                                                                      [ ok ]
Runlevel: sysinit
Dynamic Runlevel: hotplugged
Dynamic Runlevel: needed/wanted
Dynamic Runlevel: manual
/ # rc-update add sshd
 * service sshd added to runlevel sysinit
/ # rc-status
Runlevel: sysinit
 sshd                                                                                                                                                                               [  stopped  ]
Dynamic Runlevel: hotplugged
Dynamic Runlevel: needed/wanted
Dynamic Runlevel: manual
/ # openrc default
mkdir: can't create directory '/sys/fs/cgroup/openrc.sshd': Read-only file system
ssh-keygen: generating new host keys: RSA ECDSA ED25519
 * Starting sshd ...                                                                                                                                                                       [ ok ]
/ #
```
… and next we'll make a check-point, because we’re going to mess something up eventually :-) We will still always have to restart sshd in this image, but the key for the virtual machine has been generated now and will hence stay the same.
```
/ # exit
```
We ask Docker to remember the current state of the filesystem of the **container** named "dat103" as a new **image** called ``"dat103"``.
Then we delete the old container, and start a fresh one from the new image, with an additional option to be able to talk to the ssh-server inside.
For that, we'll *publish* the network port for ssh on the inside (22) as port 2222 outside (but only on the `localhost`-interface, not the whole wide world in general).

We also put the public part of our ssh key where Docker can see it.
On Windows, your `cp`-command will look slightly differently, and remember to replace `/tmp` with `${env:TMP}` as before.

```
% docker commit dat103 dat103
sha256:...
% docker images

IMAGE            ID             DISK USAGE CONTENT SIZE   EXTRA
alpine:latest    d529dd0c6e55       8.42MB             0B    U   
dat103:latest    965d00b70787        334MB             0B        
% docker rm dat103
% cp ~/.ssh/yourkey.pub /tmp
% docker run -it --name dat103 --platform linux/amd64 -v /tmp:/app -p 127.0.0.1:2222:22 dat103:latest
/ # openrc default
mkdir: can't create directory '/sys/fs/cgroup/openrc.sshd': Read-only file system
 * Starting sshd ...
/ # mkdir /root/.ssh
/ # cp /app/yourkey.pub /root/.ssh/authorized_keys
/ #
```

Now leave this as this is, i.e. **do not exit** the container this time.

## 6) Connect from the outside to ssh in the container!

Use a different window/terminal on your computer. Note that the default Alpine configuration will **not** let you log in with a root-password, you **have** to have the right public key installed on the system.
```
% ssh -p 2222 root@localhost
Welcome to Alpine!
...
1234567890:~#
```
