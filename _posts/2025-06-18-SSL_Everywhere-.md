---
layout: post
title: SSL Everywhere
---

Goal: Having a valid SSL certificate (locally).

One of the issues I had for some years was some Nextcloud features weren't running due to the lack of SSL.

Example: Nextcloud Notes and Gpodder didn't work great with a self-hosted SSL.

This is what I did:

- created a container in proxmox to be the host of a docker container. I used Ubuntu 24.04 LXC container.

- inside I have updated it and installed docker.
  
```
# Update and force upgrade all packages
sudo apt update && sudo apt upgrade -y

# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# Docker and compose
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

```

- created a docker-compose file

```
mkdir /root/nginxproxyman -p
touch /root/nginxproxyman/docker-compose.yml
```

- Added the following content

```
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
```

- Run it

```
cd /root/nginxproxyman
docker-compose up -d
```

- Login into the system `http://ip:81` and setup the basic username and password.
  
- As I'm using Cloudflare to manage my domain DNS, I had to get a Token that allows write actions into my DNS zone.

- On Nginx Proxy Manager Site click SSL certificates at the top and Add SSL Certificate, Let's Encrypt with the following domains: `*.sub.domain.com` and `sub.domain.com`. Use DNS Challenge. (don't forget you need to expose port 80 and forward it in your home router)

- Now you can create a Proxy Host for your Nextcloud.

``` in Details:
Domain: nextcloud.sub.domain.com
Scheme: https
IP: Nextcloud IP
Foward Port: 443
Cache Assets: ON
Block Comman Exploits: ON
Websockets Support: ON
Access: List: Public
```
  
``` in SSL:
SSL Certificate: *.sub.domain.com,  sub.domain.com
Force SSL: ON
HTTP/2 Support: ON
HSTS Enabled: ON
HSTS Subdomains: ON
```

And you should be set.

Another option is using Duck DNS. You can see the following video https://www.youtube.com/embed/DjKom4B4USo?si=2mTOOYuxy4Zwk7-l and tutorial: https://www.learntohomelab.com/homelabseries/EP26_nginxproxymanagerssl/


Have fun using LetEncrypt SSL in your Nextcloud, routable inside but not exposed into the internet.

AB