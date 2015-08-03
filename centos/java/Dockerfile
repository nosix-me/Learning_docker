#
# MAINTAINER        Moji,nosix <six.heyaxiang@gmail.com>
# DOCKER-VERSION    1.6.2
#
# Dockerizing CentOS7: Dockerfile for building CentOS images
#
FROM       centos:centos7.1.1503
MAINTAINER Moji,nosix <six.heyaxiang@gmail.com>

ENV TZ "Asia/Shanghai"
ENV TERM xterm

ADD aliyun-mirror.repo /etc/yum.repos.d/CentOS-Base.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

RUN yum install -y fonts-chinese curl wget tar bzip2 unzip vim-enhanced passwd sudo yum-utils hostname net-tools rsync man && \
    yum install -y gcc gcc-c++ git make automake cmake patch logrotate python-devel libpng-devel libjpeg-devel && \
    yum install -y --enablerepo=epel python-pip && \
    yum clean all

#java配置
ADD jdk-7u80-linux-x64.tar.gz /usr/local/moji
ENV JAVA_HOME /usr/local/moji/jdk1.7.0_80
ENV CLASSPATH $JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin

EXPOSE 22


