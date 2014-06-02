# An example Ubuntu container for a web application
FROM ubuntu
MAINTAINER Paul Willoughby <paul@fivetide.com>

# Update sources
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

# Required packages
RUN apt-get install -y apache2
RUN apt-get install -y php5

# Start Apache and expose port
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
EXPOSE 80


RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:screencast' |chpasswd

EXPOSE 22
CMD    /usr/sbin/sshd -D

ENTRYPOINT ["/usr/sbin/apache2"]
CMD ["-D", "FOREGROUND"]

