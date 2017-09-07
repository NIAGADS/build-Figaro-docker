FROM ubuntu:16.04
MAINTAINER Otto Valladares <ottov.upenn@gmail.com>
LABEL Description="FIGARO stack, based on Ubuntu 16.04 LTS." \
	License="Apache License 2.0" \
	Usage="docker run -it -p 80:80 ottov/figaro-basic" \
	Version="1.0"

# update OS
ENV TERM dumb
RUN apt-get update
RUN apt-get upgrade -y

# Install LAMP
RUN apt-get install -y git
RUN apt-get install -y php-cli


# Clone from master
RUN rm -fR /var/www/html
RUN git clone https://ottov123@bitbucket.org/wanglab-upenn/figaro-website.git /var/www/html

#
VOLUME /var/www/html
WORKDIR /var/www/html

EXPOSE 80

ENTRYPOINT ["php","--server","0.0.0.0:80"]
