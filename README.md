## Docker: Debian - LEP (3-Tier)

[![Build Status](https://travis-ci.org/ericmdev/docker.debian-lep-3tier.svg?branch=master)](https://travis-ci.org/ericmdev/docker.debian-lep-3tier)

**Docker orchestration** of [Debian](https://www.debian.org/) LEP ([Linux](https://www.kernel.org/) [NGINX](https://www.nginx.com/) [PHP](http://php.net/)) 3-tier stack.

*Requirements*
- [Docker](https://www.docker.com/) 

*Base Docker Image*
- [debian:jessie](https://hub.docker.com/_/debian/)

*Processes*
- nginx (1.9.9)
- php5-fpm (5.6.14)

### Clone

Clone repo with submodules or clone and pull down and initialise submodule.

    $ git submodule init
    $ git submodule update

### Development

    $ docker-compose build

Builds the `nginx`, `php` and `www` services in `docker-compose.yml`.

### Usage

    $ docker-compose up -d

Creates and starts containers.

### Host Mapping

Volumes are mapped to host `./volumes/`.
- `/var/log`
- `/var/cache/nginx`
- `/srv/www/php-app/`
