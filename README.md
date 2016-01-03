## Docker-Compose: Debian - LEP (3-Tier)

[![Build Status](https://travis-ci.org/ericmdev/docker-compose.lep-3.svg?branch=master)](https://travis-ci.org/ericmdev/docker-compose.lep-3)

**Docker orchestration** of [Debian](https://www.debian.org/) LEP ([Linux](https://www.kernel.org/) [NGINX](https://www.nginx.com/) [PHP](http://php.net/)) stack (3-tier).

*Requirements*
- [Docker](https://www.docker.com/)

*Base Docker Image*
- [debian:jessie](https://hub.docker.com/_/debian/)

*Processes*
- nginx (1.9.9)
- php5-fpm (5.6.14)

### Clone

Clone repo into your project with submodules.

    $ git clone --recursive <repo> ./docker-compose-lep-3

### Usage

    $ docker-compose up -d

Creates and starts the services in `docker-compose.yml`.

### Development

    $ docker-compose build

Builds the services in `docker-compose.yml`.

### Vagrant

    $ vagrant up

Open `192.168.33.61/index.php`.

*Plugins*
- [vagrant-docker-compose](https://github.com/leighmcculloch/vagrant-docker-compose)
    - `$ vagrant plugin install vagrant-docker-compose`

### Host Mapping

Volumes are mapped to host `./volumes/`.
- `/var/log`
- `/var/cache/nginx`
- `/srv/www/php-app/`
