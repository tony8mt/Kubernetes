FROM centos:6

RUN yum update -y
RUN yum install java -y
RUN yum install wget -y
RUN yum install unzip -y
RUN cd /etc
RUN wget http://apache.melbourneitmirror.net/tomcat/tomcat-7/v7.0.79/bin/apache-tomcat-7.0.79.zip
RUN unzip -q apache-tomcat-7.0.79.zip
RUN rm -f *.zip
RUN mv apache-* apache
RUN sed -i s/port\=\"8080\"/port\=\"5000\"/g apache/conf/server.xml
RUN chmod 755 apache/bin/*.sh
RUN ls -l apache/bin/*.sh
CMD ["apache/bin/catalina.sh", "run"]
EXPOSE 5000
