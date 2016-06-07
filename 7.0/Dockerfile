FROM debian:jessie-backports

MAINTAINER Marcelo Almeida <marcelo.almeida@jumia.com>

WORKDIR "/root"

ENV DEBIAN_FRONTEND noninteractive

# INSTALL DEPENDENCIES
RUN apt-get update && apt-get install -y curl

# ADD DOTDEB REPOS
RUN echo "deb http://packages.dotdeb.org jessie all" | tee /etc/apt/sources.list.d/dotdeb.list ;\
  echo "deb-src http://packages.dotdeb.org jessie all" | tee -a /etc/apt/sources.list.d/dotdeb.list ;\
  curl -s https://www.dotdeb.org/dotdeb.gpg | apt-key add - ;\
  apt-get update

# INSTALL PACKAGES DEPENDENCIES
RUN apt-get install -y php7.0-cli php7.0-fpm

CMD ["php", "-a"]
