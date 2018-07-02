FROM openjdk:8u121-jdk-alpine
MAINTAINER panzhengming@juxinli.com
RUN mkdir /opt/app -p 
WORKDIR /opt/app
RUN wget http://mirrors.shu.edu.cn/jenkins/war-stable/2.121.1/jenkins.war -O jenkins.war
RUN sed -i 's#dl-cdn.alpinelinux.org#mirrors.aliyun.com#g' /etc/apk/repositories && apk update
# 根据https://github.com/liumiaocn/easypack/blob/master/containers/alpine/jenkins/Dockerfile来下载alpine系统依赖
# 可以在jenkins官网上查看对应版本的alpine系统依赖包https://www.archlinux.org/packages/community/any/jenkins/
RUN apk add --no-cache docker py-pip git openssh-client curl unzip bash ttf-dejavu coreutils
RUN mkdir /root/.pip -p
ADD pip.conf /root/.pip/pip.conf
RUN pip install robotframework robotframework-requests robotframework-databaselibrary robotframework-httplibrary
VOLUME [ "/root/.jenkins" ]
EXPOSE 8080 50000
CMD [ "java", "-jar", "jenkins.war", "-Djava.awt.headless=true" ]