FROM daocloud.io/centos:7
MAINTAINER meteorsoftware@qq.com
ENV container docker
LABEL name="Centos7 Ansible Base Image" \
    vendor="Centos” \
    license="GPLv2" \
build-date="20170228”

RUN yum -y update \
    && yum -y install wget \
    && mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup \
    && wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.163.com/.help/CentOS7-Base-163.repo \
    && yum clean all \
    && yum makecache \
    && yum -y install epel-release \
    && yum -y install python-pip  \
    && yum -y install ansible \
    && echo "########################ansible####################################"\
    && ansible --version \
    && ansible-playbook --version \
    && ansible-galaxy --version
RUN yum -y install net-tools
RUN yum -y install git
RUN yum -y install vim
RUN yum -y install gcc gcc+ gcc-c++ automake autoconf libtool make 
RUN yum -y install nodejs \
    && npm install -g cnpm \
    && cnpm install -g strongloop \
    && cnpm install -g apiconnect \
    && cnpm install -g strong-pm
#ssl-pm-install --systemd && /usr/bin/systemctl start strong-pm 
#/usr/bin/systemctl start strong-pm
# cnpm install -g pm2  n 
CMD ["/bin/bash", "-c", "echo FROM daocloud.io/centos:7"]

