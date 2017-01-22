FROM kalilinux/kali-linux-docker
LABEL version="1.0" description="Dockerizing network tools"
MAINTAINER Victor Clark <victor@victorclark.org>

#Link for curl-loader. Last update 2013-06-05. Subdomain may vary
#Find current URL by using curl to do a GET request on direct link from SF
ENV CURL_LOADER_LINK https://netcologne.dl.sourceforge.net/project/curl-loader/curl-loader-stable/curl-loader-0.56/curl-loader-0.56.tar.bz2
ENV CURL_LOADER_DIR curl-loader-0.56

#Install some useful tools:
RUN \
    apt-get update && \
    apt-get install -y \
    binutils \
    build-essential \
    bzip2 \
    curl \
    gcc \
    hping3 \
    ipython \
    less \
    lft \
    libssl-dev \
    make \
    net-tools \
    openssl \
    python \
    tar \
    traceroute \
    tmux \
    vim \
    zlib1g-dev
#zlib1g-dev not needed on debian-bsaed build

#Download, compile, and create link for curl-loader
WORKDIR tmp
RUN curl -X GET $CURL_LOADER_LINK -o curl-loader.tar.bz2
RUN tar xjf curl-loader.tar.bz2
WORKDIR /tmp/$CURL_LOADER_DIR/
RUN make
RUN ln -s /tmp/$CURL_LOADER_DIR/curl-loader /bin/curl-loader

#Put out the welcome mat
WORKDIR /pyping2
ENTRYPOINT /bin/bash