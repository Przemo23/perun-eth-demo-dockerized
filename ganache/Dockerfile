FROM golang:1.15.6-alpine3.12
RUN apk --no-cache add gcc g++ make ca-certificates
RUN apk add nodejs npm
RUN npm install -g ganache-cli
RUN apk add linux-headers
RUN mkdir /app
WORKDIR /app
RUN apk update -qq && apk add git
ENTRYPOINT ifconfig
ENTRYPOINT ganache-cli -d -p 8081 -h 0.0.0.0 --account='0x6aeeb7f09e757baa9d3935a042c3d0d46a2eda19e9b676283dce4eaf32e29dc9,100000000000000000000000' --account='0x7d51a817ee07c3f28581c47a5072142193337fdca4d7911e58c5af2d03895d1a,100000000000000000000000' --account='0x6aeeb7f09e757baa9d3935a042c3d0d46a2eda19e9b676283dce4eaf32e29dc0,100000000000000000000000' --block-time 5 
