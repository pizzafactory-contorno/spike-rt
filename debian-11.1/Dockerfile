FROM pizzafactory0contorno/piatto:debian-11.1@sha256:47d93bf6779941ab45f4baa872a850746952db9c0a81a9dfd312ced71f17c74a

LABEL maintainer="Masaki Muranaka <monaka@monami-ya.com>"

ARG GCC_URL=https://developer.arm.com/-/media/Files/downloads/gnu-rm/10.3-2021.10/gcc-arm-none-eabi-10.3-2021.10-x86_64-linux.tar.bz2

USER root
RUN apt-get update && apt-get upgrade -y \
 && apt-get install -y --no-install-recommends ruby2.7 bzip2 curl make libncurses5 python3 git \
 && rm -rf /var/lib/apt/lists/* \
 && gem install shell \
 && curl -L ${GCC_URL} -o gcc-arm-none-eabi.tar.bz2 \
 && mkdir -p  /usr/local/gcc-arm-none-eabi \
 && tar -xf ./gcc-arm-none-eabi.tar.bz2 -C /usr/local/gcc-arm-none-eabi --strip-components=1 \
 && rm -rf ./gcc-arm-none-eabi.tar.bz2 
USER user

ENV PATH $PATH:/usr/local/gcc-arm-none-eabi/bin

