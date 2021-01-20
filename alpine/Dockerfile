FROM alpine:latest
LABEL "app"="gns3"
LABEL "jenis"="node"
RUN apk update && apk add tmux openssh nmap nmap-scripts curl git ca-certificates wget rsync unzip tcpdump jq nmap-ncat socat tshark python3 py3-virtualenv nano vim 
#RUN apk add --no-cache gcc libc-dev g++ musl-dev python3-dev linux-headers psutils psutils-dev
#RUN pip3 install gns3-server
RUN rm -rf /tmp/* /var/cache/apk/*
#RUN mkdir -p /gns3volumes && ln -s /usr/lib/python3.8/site-packages/gns3server/compute/docker/resources/ /gns3
#RUN mkdir -p /gns3volumes && cp -r /usr/lib/python3.8/site-packages/gns3server/compute/docker/resources/ /gns3
RUN mkdir -p /super/
ADD run.sh /super/run.sh 
RUN chmod a+x /super/run.sh
ENTRYPOINT ["sh","-C","/super/run.sh"]
