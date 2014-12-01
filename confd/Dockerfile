FROM ubuntu:14.04
MAINTAINER Dan McAulay
ENV REFRESHED_AT 2014-11-30

RUN apt-get -yqq update
RUN apt-get -yqq install nginx curl

RUN mkdir -p /etc/confd/{conf.d,templates}
ADD nginx.toml /etc/confd/conf.d/
ADD nginx.tmpl /etc/confd/templates/
ADD nginx.conf /etc/nginx/

RUN curl -qL https://github.com/kelseyhightower/confd/releases/download/v0.5.0/confd-0.5.0-linux-amd64 -o /usr/local/bin/confd
ADD confd-watch /usr/local/bin/confd-watch

RUN chmod +x /usr/local/bin/confd
RUN chmod +x /usr/local/bin/confd-watch

RUN rm /etc/nginx/sites-enabled/default

EXPOSE 80
