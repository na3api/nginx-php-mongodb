FROM nginx:latest

ADD nginx.conf /etc/nginx/
ADD site.conf /etc/nginx/conf.d/default.conf

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data
