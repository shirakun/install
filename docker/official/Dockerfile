FROM alpine:latest

MAINTAINER admin@v2ray.com

WORKDIR /tmp/v2ray

RUN apk add --update curl unzip
RUN curl -o /tmp/v2ray/go.sh https://install.direct/go.sh
RUN chmod +x /tmp/v2ray/go.sh
RUN /tmp/v2ray/go.sh --nosystemintegration
RUN rm -rf /tmp/v2ray
RUN rm -rf /var/cache/apk/*

ENV PATH /usr/bin/v2ray/;$PATH

COPY config.json /etc/v2ray/config.json

CMD ["v2ray", "-config=/etc/v2ray/config.json"]
