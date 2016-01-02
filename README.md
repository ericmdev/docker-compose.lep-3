## Docker: Debian - LEP (3-Tier)

**Docker orchestration** of 3-tier [Debian](https://www.debian.org/) LEP ([Linux](https://www.kernel.org/) [NGINX](https://www.nginx.com/) [PHP](http://php.net/)) stack.

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
