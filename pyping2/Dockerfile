#uncomment below for x86 image
FROM debian:latest

#uncomment below for RPI image  
#FROM armhf/debian:latest   

#Link for curl-loader. Last update 2013-06-05. Subdomain may vary
#Find current URL by using curl to do a GET request on direct link from SF
ENV CURL_LOADER_LINK https://netcologne.dl.sourceforge.net/project/curl-loader/curl-loader-stable/curl-loader-0.56/curl-loader-0.56.tar.bz2
ENV CURL_LOADER_DIR curl-loader-0.56

RUN \
    apt-get update && \
    apt-get install -y \
    binutils \
    build-essential \
    bzip2 \
    curl \
    gcc \
    hping3 \
    # ipython \
    less \
    lft \
    libssl-dev                #required for curl-loader \
    make \
    # net-tools                 #install ifconfig, etc \
    openssl                   #required for curl-loader \
    # python
    tar \
    traceroute
    # tmux                      #can replace with screen \
    # vim                       #replace with your editor of choice \
    

# RUN ["curl", "\-X ", "GET", "\-o", $CURL_LOADER_LINK curl-loader.tar.bz2]
# RUN ["tar", "xjf", "curl-loader.tar.bz2"]

#Compile curl-loader
WORKDIR tmp
RUN curl -X GET $CURL_LOADER_LINK -o curl-loader.tar.bz2
# RUN mkdir curl-loader
# RUN tar xjf curl-loader.tar.bz2 -C curl-loader
RUN tar xjf curl-loader.tar.bz2
WORKDIR /tmp/$CURL_LOADER_DIR/
RUN make
RUN ln -s /tmp/$CURL_LOADER_DIR /bin/curl-loader

WORKDIR /pyping2
ENTRYPOINT /bin/bash
