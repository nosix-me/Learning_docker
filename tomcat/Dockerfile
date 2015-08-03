#
# MAINTAINER        Moji,Nosix <six.heyaxiang@gmail.com>
# DOCKER-VERSION    1.7.1
#
# Dockerizing Tomcat:simple tomcat web service
#
FROM centos:java
MAINTAINER        Moji,Nosix <six.heyaxiang@gmail.com>


#tomcat配置
ADD apache-tomcat-7.0.63.tar.gz /opt/
RUN cd /opt/ && mv apache-tomcat-7.0.63 apache-tomcat 
ENV CATALINA_HOME /opt/apache-tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
WORKDIR $CATALINA_HOME

EXPOSE 8080

CMD ["catalina.sh", "run"]


