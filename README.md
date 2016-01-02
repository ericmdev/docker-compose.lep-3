## Docker: Debian - LEP (3-Tier)

**Docker orchestration** of [Debian](https://www.debian.org/) LEP ([Linux](https://www.kernel.org/) [NGINX](https://www.nginx.com/) [PHP](http://php.net/)) 3-tier stack.

*Requirements*
- [Docker](https://www.docker.com/) 

*Base Docker Image*
- [debian:jessie](https://hub.docker.com/_/debian/)

*Processes*
- NGINX (1.9.9)
- PHP-FPM (5.6.14)
- Data (/srv/www/)

### Clone

Clone repo with git submodules or clone and pull down and initialise submodule files.

    $ git submodule init
    $ git submodule update

### Development

    $ docker-compose build

Builds the `nginx`, `php` and `www` services in `docker-compose.yml`.

### Usage

    $ docker-compose up -d

Creates and starts containers.
