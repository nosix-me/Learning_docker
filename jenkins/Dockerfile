# MAINTAINER        Moji, nosix <six.heyaxiang@gmail.com>
#
# Dockerizing Jenkins: Dockerfile for building Jenkins images
#
FROM       centos:java
MAINTAINER Moji, nosix <six.heyaxiang@gmail.com>

ENV JENKINS_HOME /var/jenkins_home
ENV JENKINS_VERSION 1.609.1
ENV JENKINS_UC https://updates.jenkins-ci.org
ENV COPY_REFERENCE_FILE_LOG /var/log/copy_reference_file.log

RUN useradd -d "$JENKINS_HOME" -u 1000 -m -s /bin/bash jenkins

RUN mkdir -p /usr/share/jenkins/ref/init.groovy.d

COPY init.groovy /usr/share/jenkins/ref/init.groovy.d/tcp-slave-agent-port.groovy
COPY jenkins.war /usr/share/jenkins/jenkins.war

RUN cd /usr/share/jenkins/ && \
    chown -R jenkins "$JENKINS_HOME" /usr/share/jenkins/ref && \
    touch $COPY_REFERENCE_FILE_LOG && chown jenkins.jenkins $COPY_REFERENCE_FILE_LOG

USER jenkins

VOLUME /var/jenkins_home

EXPOSE 8080 50000

COPY jenkins.sh /usr/local/bin/jenkins.sh

ENTRYPOINT ["/usr/local/bin/jenkins.sh"]
