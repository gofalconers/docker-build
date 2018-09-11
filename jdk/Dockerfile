FROM 172.17.16.118/ci/centos:6.9
MAINTAINER panzhengming@2345.com
COPY jdk-8u181-linux-x64.tar.gz /tmp/jdk-8u181-linux-x64.tar.gz 

RUN tar -zxvf /tmp/jdk-8u181-linux-x64.tar.gz -C /opt > : && rm -rf /tmp/*

ENV JAVA_HOME=/opt/jdk1.8.0_181
ENV CLASSPATH=.:$JAVA_HOME/lib/tools.jar:$JAVA_HOME/lib/dt.jar 
ENV PATH=$JAVA_HOME/bin:$HOME/bin:$HOME/.local/bin:$PATH
