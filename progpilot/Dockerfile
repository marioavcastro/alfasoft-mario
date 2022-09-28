FROM php:7-cli
RUN apt-get update
RUN apt-get install -y zip
COPY composer.json /progpilot/
ADD https://getcomposer.org/download/1.6.5/composer.phar /progpilot/
WORKDIR /progpilot
RUN php composer.phar install
COPY wrapper.php /progpilot/
COPY analyzer /
ENTRYPOINT []
CMD ["/analyzer", "run"]
