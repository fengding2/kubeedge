FROM golang:1.13

ADD edgemesh-iptables.sh /usr/local/bin
RUN apt-get update && apt-get install -y iproute2 iptables vim net-tools

ENTRYPOINT ["/usr/local/bin/edgemesh-iptables.sh"]
