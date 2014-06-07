
FROM     ubuntu
MAINTAINER Dien Vu "dien@mobgame.vn"

# make sure the package repository is up to date
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

# install apache + php
RUN apt-get install -y apache2
RUN apt-get install -y php5
RUN apt-get install -y php5-mcrypt
RUN apt-get install -y git

RUN git clone https://github.com/nicolasff/phpredis.git

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

# install ssh-server
RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:123456' |chpasswd

ADD ./startup.sh /opt/startup.sh
RUN chmod 0755 /opt/startup.sh

EXPOSE 80
EXPOSE 22

ENTRYPOINT ["/opt/startup.sh"]


