FROM php:7.0-fpm

RUN apt-get update && \
     apt-get install -y sudo && \
     apt-get install -y curl nano && \
     apt-get install -y git-all

RUN apt-get install -y --no-install-recommends libpq-dev && \
	 docker-php-ext-install mysqli pdo_pgsql pdo_mysql

RUN \
    apt-get update && \
    apt-get install libldap2-dev -y && \
    rm -rf /var/lib/apt/lists/* && \
    docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu/ && \
    docker-php-ext-install ldap
