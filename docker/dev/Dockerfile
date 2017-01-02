FROM golang:latest

MAINTAINER admin@v2ray.com

RUN mkdir /usr/bin/v2ray/
RUN mkdir /etc/v2ray/
RUN mkdir /var/log/v2ray/
RUN go get -u v2ray.com/core/...
RUN go generate v2ray.com/core/...
RUN go install v2ray.com/core/tools/build
RUN build -dir /usr/bin/v2ray

ENV PATH /usr/bin/v2ray/:$PATH

EXPOSE 8000
COPY config.json /etc/v2ray/config.json

CMD ["v2ray", "-config=/etc/v2ray/config.json"]
