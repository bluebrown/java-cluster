FROM tomcat:9.0

WORKDIR /usr/local/tomcat/lib
RUN curl https://repo1.maven.org/maven2/de/javakaffee/msm/memcached-session-manager/2.3.2/memcached-session-manager-2.3.2.jar \
  > memcached-session-manager-2.3.2.jar

RUN curl https://repo1.maven.org/maven2/de/javakaffee/msm/memcached-session-manager-tc9/2.3.2/memcached-session-manager-tc9-2.3.2.jar \
  > memcached-session-manager-tc9-2.3.2.jar

RUN curl https://repo1.maven.org/maven2/net/spy/spymemcached/2.9.1/spymemcached-2.9.1.jar > spymemcached-2.9.1.jar

WORKDIR /usr/local/tomcat

RUN echo "de.javakaffee.web.msm.level=FINE" >> conf/logging.properties && \
 echo "net.spy.memcached.level = WARNING" >> conf/logging.properties && \
 echo "net.spy.memcached.MemcachedConnection.level = WARNING" >> conf/logging.properties

ADD setenv.sh /usr/local/tomcat/bin/setenv.sh
ADD sample.war /usr/local/tomcat/webapps/sample.war
ADD context.xml /usr/local/tomcat/conf/context.xml
ADD server.xml /usr/local/tomcat/conf/server.xml

EXPOSE 8080
