FROM debian:stretch
MAINTAINER Liu Chong <mail@clojure.cn>
WORKDIR /root
RUN apt-get update && \
    apt-get install --no-install-recommends -y \
    build-essential ca-certificates curl file xutils-dev && \
    rm -rf /var/lib/apt/lists/*
RUN curl https://sh.rustup.rs -sSf | \
    sh -s -- --default-toolchain beta -y
ENV PATH=/root/.cargo/bin:$PATH \
    SSL_VERSION=1.0.2h
RUN curl https://www.openssl.org/source/openssl-$SSL_VERSION.tar.gz -O && \
    tar -xzf openssl-$SSL_VERSION.tar.gz && \
    cd openssl-$SSL_VERSION && ./config && make depend && make install && \
    cd .. && rm -rf openssl-$SSL_VERSION*
ENV OPENSSL_LIB_DIR=/usr/local/ssl/lib \
    OPENSSL_INCLUDE_DIR=/usr/local/ssl/include \
    OPENSSL_STATIC=1
