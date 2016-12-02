FROM alpine:latest

MAINTAINER admin@v2ray.com

WORKDIR /tmp/v2ray

RUN apk add --update curl unzip
RUN mkdir /usr/bin/v2ray/
RUN mkdir /etc/v2ray/
RUN mkdir /var/log/v2ray/

RUN VER="$(curl -s https://api.github.com/repos/v2ray/v2ray-core/releases/latest | grep 'tag_name' | cut -d\" -f4)" && \
    curl -L -H "Cache-Control: no-cache" -o "/tmp/v2ray/v2ray.zip" "https://github.com/v2ray/v2ray-core/releases/download/${VER}/v2ray-linux-64.zip" &&
    unzip "/tmp/v2ray/v2ray.zip" -d "/tmp/v2ray/" && \
    cp "/tmp/v2ray/v2ray-${VER}-linux-64/v2ray" "/usr/bin/v2ray/v2ray"

RUN rm -rf /tmp/v2ray
RUN rm -rf /var/cache/apk/*

ENV PATH /usr/bin/v2ray/;$PATH

COPY config.json /etc/v2ray/config.json

CMD ["v2ray", "-config=/etc/v2ray/config.json"]
