FROM kalilinux/kali-linux-docker:latest
#Note this image has only two tags: latest and rolling
LABEL version="1.0" description="Kali with extra tools"
MAINTAINER Victor Clark <victor@victorclark.org>

RUN \
    apt-get update && \
    apt-get install -y \
        arp-scan \
        hping3 \
        lft \
        netdiscover \
        nmap \
        traceroute

ENTRYPOINT /bin/bash