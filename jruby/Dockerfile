FROM        alpine:latest
MAINTAINER  Naner Nunes

ARG         VERSION="9.1.6.0"
ENV         PATH  /usr/local/jruby-${VERSION}:${PATH}

RUN         apk --no-cache add bash tar libc6-compat openjdk8-jre-base

ADD         https://s3.amazonaws.com/jruby.org/downloads/${VERSION}/jruby-bin-${VERSION}.tar.gz /tmp
RUN         tar -zxvf /tmp/jruby-bin-${VERSION}.tar.gz --strip 1 -C /usr/local

ENTRYPOINT  ["jruby"]
CMD         ["--help"]
