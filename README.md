# nginx-reverse-proxy-docker

In the recent blog posts we presented how to embed Husarnet Client inside a Docker container. This solution is fine, however has a few drawbacks like:
- you need to modify your existing containers
- you need to install one instance of Husarnet Client per each container you want to connect (and manage multiple hostnames)

To overcome those issues we introduce an official [Husarnet Docker Image](https://hub.docker.com/r/husarnet/husarnet), that utilizes a [sidecar Docker design pattern](https://www.magalix.com/blog/the-sidecar-pattern). You can run this container next to your existing containers to share the VPN network from a Husarnet Container to one or multiple other containers at once.

![Husarnet Docker Contatainer VPN sidecar](docs/cover-image.png)



## use cases

### 1. saving IP addresses space

you need only one public IP address associated with your reverse proxy server. Other services can be hosted even from your local LAN network, even if you have dynamic IP.

### 2. running a website from your laptop / Raspberry Pi

### 3. security - your application servers do not need to has public or static IP at all

### 4. 

## important files to make hostnames work

understanding hostname resolution (why `resolver 127.0.0.11` works):


(https://serverfault.com/questions/118923/difference-between-etc-hosts-and-etc-resolv-conf)


1. `/etc/hosts`

```bash
docker exec -it <container id> cat /etc/hosts

...

```

2. `/etc/nsswitch.conf`

```bash
docker exec -it <container id> cat /etc/hosts

...

```

3. `/etc/resolv.conf`

```bash
docker exec -it <container id> cat /etc/hosts

...

```