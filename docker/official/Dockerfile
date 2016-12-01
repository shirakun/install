FROM alpine:latest

MAINTAINER admin@v2ray.com

RUN apk add --update curl unzip
RUN curl -O https://install.direct/go.sh
RUN chmod +x ./go.sh
RUN ./go.sh --nosystemintegration
RUN rm ./go.sh
RUN rm -rf ./v2ray*
RUN rm -rf /var/cache/apk/*

ENV PATH /usr/bin/v2ray/;$PATH

COPY config.json /etc/v2ray/config.json

CMD ["v2ray", "-config=/etc/v2ray/config.json"]
