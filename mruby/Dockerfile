FROM        alpine:latest
MAINTAINER  Naner Nunes

ARG         APKS="bison gcc g++ ruby git"

RUN         apk --no-cache add $APKS                  && \
            git clone https://github.com/mruby/mruby  && \
            mruby/minirake -C mruby                   && \
            cp mruby/bin/* /usr/local/bin/            && \
            apk del $APKS && rm -rf mruby

ENTRYPOINT  ["mruby"]
CMD         ["--help"]
