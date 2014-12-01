FROM ubuntu:14.04
MAINTAINER Dan McAulay
ENV REFRESHED_AT 2014-11-29

RUN apt-get -yqq update
RUN apt-get -yqq install apache2

RUN echo "<h1>Running from Docker on CoreOS</h1>" > /var/www/html/index.html

