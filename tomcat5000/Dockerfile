FROM centos
MAINTAINER “Tony Thomas” <tonyt@gmail.com>
ENV container docker
RUN yum -y update; yum clean all
RUN yum -y install java; yum clean all
RUN yum -y install unzip; yum clean all
RUN yum -y install wget; yum clean all
RUN cd /etc; wget http://apache.mirror.serversaustralia.com.au/tomcat/tomcat-8/v8.5.15/bin/apache-tomcat-8.5.15.zip;\
unzip /etc/apache-tomcat-8.5.15.zip;\
mv /etc/apache-tomcat-8.5.15 /etc/tomcat;\
mv /etc/tomcat/conf/server.xml /etc/tomcat/conf/server.xml.bkp;\
(sed 's/port\=\"8080\"/port\=\"5000\"/g' /etc/tomcat/conf/server.xml.bkp > /etc/tomcat/conf/server.xml);\
chmod 755 /etc/tomcat/bin/*.sh;
CMD [ "sh", "-c", "/etc/tomcat/bin/startup.sh" ] 
EXPOSE 5000
CMD [“/usr/sbin/init”]
