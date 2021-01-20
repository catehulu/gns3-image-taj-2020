FROM alpine:3.8
RUN apk update && apk add quagga openrc vim supervisor tmux screen
#RUN apk add --no-cache gcc libc-dev g++ musl-dev python3-dev linux-headers psutils psutils-dev
#RUN pip3 install gns3-server
#RUN mkdir -p /gns3volumes && ln -s /usr/lib/python3.8/site-packages/gns3server/compute/docker/resources/ /gns3
RUN mkdir -p /superv
COPY daemons /etc/quagga/daemons
COPY zebra.conf /etc/quagga/zebra.conf
COPY quagga.conf /etc/quagga/Quagga.conf
COPY ospfd.conf /etc/quagga/ospfd.conf
COPY bgpd.conf /etc/quagga/bgpd.conf
COPY ripngd.conf /etc/quagga/ripngd.conf
ADD supervisord.conf /superv/
ADD run.sh /superv/
ADD screenrc /superv/
LABEL "app"="gns3"
LABEL "jenis"="router"
ENTRYPOINT ["sh","-C","/superv/run.sh"]
#ENTRYPOINT ["/usr/bin/supervisord","--nodaemon","--configuration","/superv/supervisord.conf"]
