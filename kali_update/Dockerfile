FROM kalilinux/kali-linux-docker
LABEL version="1.0" description="Kali with extra tools"
MAINTAINER Victor Clark <victor@victorclark.org>

RUN \
    apt-get update \
    get-get install -y \
        arp-scan \
        hping3 \
        lft \
        netdiscover \
        net-tools \
        nmap \
        traceroute \
        vim

ENTRYPOINT /bin/bash