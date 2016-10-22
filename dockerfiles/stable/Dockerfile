FROM ubuntu:14.04
WORKDIR /root
RUN apt-get update && \
    apt-get install --no-install-recommends -y \
    build-essential ca-certificates curl file xutils-dev libssl-dev && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean
RUN curl https://sh.rustup.rs -sSf | \
    sh -s -- --default-toolchain stable -y
ENV PATH=/root/.cargo/bin:$PATH
