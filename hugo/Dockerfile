FROM centos as build
RUN yum install wget -y && \
    wget -O /tmp/hugo.tar.gz https://github.com/gohugoio/hugo/releases/download/v0.45.1/hugo_0.45.1_Linux-64bit.tar.gz && \
    tar -zxvf /tmp/hugo.tar.gz -C /opt && \
    mv /opt/hugo /usr/local/bin/hugo && mkdir /opt/app && rm -f /tmp/hugo.tar.gz
ADD . /opt/app
WORKDIR /opt/app
RUN hugo

FROM nginx
COPY --from=build /opt/app/public/* /usr/share/nginx/html