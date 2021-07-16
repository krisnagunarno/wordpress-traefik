# wordpress-traefik

Here is the guide for you, content creator, to deploy your own WordPress on your server. Hope this guide can be useful for you.

## Prerequisites
You must have every single requirements below to accomplish this guide:
1. Access to Linux server (Ubuntu/RedHat Preferred)
2. Docker and Docker-Compose installed on the server.
3. Patience to debug/troubleshoot every problems in this guide.

## Installation

1. Well, please clone this repository first, look at the file structures, and we will begin at traefik folder.
2. Create external network for Traefik
```bash
docker network create traefik
```
3. Please change the email and domain name in the docker-compose-traefik.yml file according with your own. SSL Certificate is already automated with CertBot (LetsEncrypt)
```bash
docker-compose up -f docker-compose-traefik.yml -d
```
4. Now move at the beginning directory, we can deploy WordPress itself with the database (MySQL) and caching tools (Redis) with docker-compose-wordpress-traefik.yml.
```bash
docker-compose up -f docker-compose-traefik.yml -d
```
5. Want to scale up the WordPress itself? Just type:
```bash
docker-compose up -f docker-compose-traefik.yml -d --scale wordpress=2
```
6. You can scale up the nodes according to the service name (wordpress, db)


## Results

Just check at https://traefik.krisna.xyz (Because the newest regulation from AWS educate to shut off every service after the session is ended, the website maybe cannot be accessed) Please contact me further at matiuskrisna24@gmail.com to activate the website
