# Componette - Docker configuration

## Containers

1. data [busybox] 
    - Application data

2. db [mariadb:10.1]
    - MariaDB

3. nginx [nginx:1.9]
    - Nginx

4. php7 [php:7-fpm]
    - PHP 7.0
    - Ssmtp
    - Rsyslog
    - Cron

## Install

Clone this branch to your server.

### Nginx

- **Strong DHE paramater**

Generate strong DHE parameter.

```sh
$ sudo openssl dhparam -outform pem -out dhparam2048.pem 2048
```

- **SSL certificates**

Generate strong self-signed certificate.

```sh
$ sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout componette.key -out componette.crt
```

### Ssmtp

Fill SMTP configuration in `ssmtp/ssmtp.conf`.

### MariaDB

Fill credentials in `docker-compose.yml`.

Defaults:
- user: root/dockerroot
- user: docker/docker
- database: docker

## Usage

Just run `docker-compose up`

## Logs

All logs you can collect over `docker-composer logs`
