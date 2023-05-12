FROM docker.io/nginx:latest

COPY nginx.conf /etc/nginx/nginx.conf
COPY default.conf /etc/nginx/conf.d/

RUN touch /run/nginx.pid \
    && chown nginx /var/log/nginx /var/cache/nginx/ /run/nginx.pid

USER nginx
