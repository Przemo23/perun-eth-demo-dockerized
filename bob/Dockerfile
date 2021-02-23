FROM golang:1.15.6-alpine3.12
RUN apk --no-cache add gcc g++ make ca-certificates
RUN apk add nodejs npm
RUN npm install -g ganache-cli
RUN apk add linux-headers
RUN mkdir /app
ADD . /app
WORKDIR /app
RUN apk update -qq && apk add git
RUN go build 
ENTRYPOINT ./perun-eth-demo demo --config bob.yaml
