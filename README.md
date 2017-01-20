# Docker + Koken + nginx = ♥

This is a fork of the official [Koken Docker image](https://github.com/koken/docker-koken-lemp) It differs from the original in
that it uses docker-compose to build and manage [Koken](http://koken.me) and MySQL in two separate containers.

## Features

* Automatically sets up and configures the database for Koken and skips that step in the installation process.
* Adds a cron job to do periodic cleanup of the image cache.
* nginx/PHP configured for best Koken performance.
* Can be used on any machine with Docker and docker-compose installed.

## Using at Digital Ocean

[Digital Ocean](https://www.digitalocean.com/?refcode=b57390666b79) provides fast, low cost virtual servers that are well suited for Koken. We have a [dedicated article on our help site](http://help.koken.me/customer/portal/articles/1648433-using-koken-docker-and-digital-ocean) with instructions on how to use this Docker image at Digital Ocean.

## General usage

If you aren't using Digital Ocean, you just need to ensure that your host is compatible with Docker and then follow the instructions below. 

1. Install [Docker](https://www.docker.io/gettingstarted/#h_installation).
2. Start the container with docker-compose

~~~bash
docker-compose up
~~~

This forwards port 80 on your host machine to the instance of Koken running on port 8080 inside the container. You can now access your new Koken install by loading the IP address or domain name for your host in a browser. Your files reside in `./koken-storage` on the host machine, while the MySQL data lives in the docker volume `dockerkokenlemp_mysql-data`.
