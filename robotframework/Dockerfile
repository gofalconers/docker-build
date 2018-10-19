FROM alpine
RUN sed -i 's#dl-cdn.alpinelinux.org#mirrors.aliyun.com#g' /etc/apk/repositories && \ 
    apk update && apk add python2 && \
    mkdir /root/.pip -p
COPY pip.conf /root/.pip/pip.conf
RUN mkdir /opt/app -p
WORKDIR /opt/app
COPY requirements.txt /tmp/require

ments.txt
RUN pip install -r /tmp/requirements.txt
