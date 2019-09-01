FROM ubuntu

ENV DEBIAN_FRONTEND=noninteractive

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_RUN_DIR /var/run/apache2
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2

RUN apt-get update
RUN apt-get install -y apache2
RUN apt-get install -y python
RUN apt-get install -y php
RUN apt-get install -y time
RUN apt-get install -y binutils
RUN echo "ServerName localhost" | tee /etc/apache2/conf-available/fqdn.conf
RUN a2enconf fqdn

EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]

RUN rm /var/www/html/index.html