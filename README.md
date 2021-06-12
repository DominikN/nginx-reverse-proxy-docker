# nginx-reverse-proxy-docker

## use cases

### 1. saving IP addresses space

you need only one public IP address associated with your reverse proxy server. Other services can be hosted even from your local LAN network, even if you have dynamic IP.

### 2. running a website from your laptop / Raspberry Pi

### 3. security - your application servers do not need to has public or static IP at all

### 4. 

## important files to make hostnames work

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