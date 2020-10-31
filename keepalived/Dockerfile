FROM centos

RUN yum update -y && yum install -y keepalived

ADD keepalived.conf /etc/keepalived/keepalived.conf
ADD state.sh  /usr/local/bin/keepalived.state.sh

CMD [ "keepalived", "-n", "-l" ]