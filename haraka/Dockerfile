FROM node:alpine
RUN mkdir /opt/haraka -p
WORKDIR /opt/haraka
RUN npm config set registry https://registry.npm.taobao.org && \
    npm install -g Haraka
CMD