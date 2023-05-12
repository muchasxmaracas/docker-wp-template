FROM wordpress:fpm-alpine

RUN { \
    		echo 'opcache.memory_consumption=256'; \
    		echo 'opcache.interned_strings_buffer=16'; \
    		echo 'opcache.max_accelerated_files=100000'; \
    		echo 'opcache.revalidate_freq=1'; \
    		echo 'opcache.fast_shutdown=1'; \
	} > /usr/local/etc/php/conf.d/opcache-recommended.ini

RUN sed -i 's/pm.max_children = 5/pm.max_children = 25/g' /usr/local/etc/php-fpm.d/www.conf; \
    sed -i 's/pm.start_servers = 2/pm.start_servers = 4/g' /usr/local/etc/php-fpm.d/www.conf; \
    sed -i 's/pm.min_spare_servers = 1/pm.min_spare_servers = 2/g' /usr/local/etc/php-fpm.d/www.conf; \
    sed -i 's/pm.max_spare_servers = 3/pm.max_spare_servers = 10/g' /usr/local/etc/php-fpm.d/www.conf; \
    sed -i 's/;pm.max_requests = 500/pm.max_requests = 500/g' /usr/local/etc/php-fpm.d/www.conf;

USER www-data
