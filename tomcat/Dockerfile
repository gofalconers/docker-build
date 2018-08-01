FROM dhub.juxinli.com/ci/maven:3.5.3-jdk-8 as build

RUN mkdir /opt/build -p
WORKDIR /opt/build
COPY . /opt/build
RUN git branch
RUN mvn clean install

FROM demo

COPY --from=build /opt/build/cashloan-api/target/*.war /opt/cashloan/webapps

EXPOSE 8080

CMD [ "catalina.sh", "run" ]