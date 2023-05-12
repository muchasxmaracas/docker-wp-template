# WP Docker Template


## Prerequisites

* Your own domain -> otherwise set an entry in /etc/hosts
* SSL via ACME -> otherwise change SSL settings in reverse proxy config


## Secrets

`cp .env.dist .env`

* Enter users and passwords


## Reverse proxy

`mv proxy/mydomain.com.conf /etc/nginx/sites-available/mydomain.com.conf`


Enter domain including TLD (e.g.: google.com)

`MYDOMAIN=enteryourdomainhere`

`echo $MYDOMAIN`

`sed -i s/mydomain\.com/$MYDOMAIN/g /etc/nginx/sites-available/mydomain.com.conf`

`mv /etc/nginx/sites-available/mydomain.com.conf /etc/nginx/sites-available/$MYDOMAIN.conf

`ln -s /etc/nginx/sites-available/$MYDOMAIN.conf /etc/sites-enabled/$MYDOMAIN.conf`

## Start containers

`docker compose up --build -d`


### Go to your domain and you should see the WP setup routine
