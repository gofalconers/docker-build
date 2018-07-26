FROM maven:3.5.3-jdk-8 as build
RUN mkdir /opt/manado_api
WORKDIR /opt/manado_api
COPY . /opt/manado_api
RUN mvn package -Dmaven.test.skip=true -P docker

FROM java:8u111-alpine
MAINTAINER panzhengming@juxinli.com
RUN mkdir /opt/manado_api -p
WORKDIR /opt/manado_api
ENV MANADO_DB_HOST=127.0.0.1
ENV MANADO_DB_DATABASE=manado_api
ENV DK_DB_HOST=127.0.0.1
ENV DK_DB_DATABASE=dk
COPY --from=build /opt/manado_api/target/*.jar /opt/manado_api
CMD [ "java", "-jar", "*.jar" ]
