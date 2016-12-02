FROM alpine:latest

MAINTAINER admin@v2ray.com

RUN mkdir /usr/bin/v2ray/ \
    && mkdir /etc/v2ray/ \
    && mkdir /var/log/v2ray/
COPY v2ray /usr/bin/v2ray/
RUN chmod +x /usr/bin/v2ray/v2ray
COPY config.json /etc/v2ray/config.json

ENV PATH /usr/bin/v2ray:$PATH

CMD ["v2ray", "-config=/etc/v2ray/config.json"]
