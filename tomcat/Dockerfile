FROM 172.17.16.118/ci/centos:6.9
MAINTAINER panzhengming

COPY jdk-8u181-linux-x64.tar.gz /tmp/jdk-8u181-linux-x64.tar.gz
RUN tar -zxvf /tmp/jdk-8u181-linux-x64.tar.gz -C /opt && \
    rm -rf /tmp/*

COPY apache-tomcat-8.5.33.tar.gz /tmp/apache-tomcat-8.5.33.tar.gz
RUN tar -zxvf /tmp/apache-tomcat-8.5.33.tar.gz -C /opt && \ 
    mv /opt/apache-tomcat-8.5.33 /opt/tomcat && \
    rm -rf /tmp/*

ENV JAVA_HOME="/opt/jdk1.8.0_181" 
ENV CLASSPATH="$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar" 
ENV CATALINA_HOME="/opt/tomcat"
ENV PATH="${CATALINA_HOME}/bin:$JAVA_HOME/bin:$PATH"

WORKDIR /opt/tomcat
EXPOSE 8080

# HEALTHCHECK --interval=15s --timeout=2s --retries=12 CMD curl --silent --fail http://localhost:8080 || exit 1

ENTRYPOINT ["catalina.sh", "run"]