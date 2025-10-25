FROM ubuntu:22.04
ARG BCC_VERSION=v0.35.0

# from https://github.com/iovisor/bcc/blob/master/INSTALL.md#install-build-dependencies-1
# - use packages for jammy
RUN apt-get update && apt-get install -y zip bison build-essential cmake flex git libedit-dev \
    libllvm14 llvm-14-dev libclang-14-dev python3 python3-pip python-is-python3 build-essential python3-dev zlib1g-dev libelf-dev libfl-dev python3-setuptools \
    liblzma-dev libdebuginfod-dev arping netperf iperf \
    && rm -rf /var/lib/apt/lists/*

# follows: https://github.com/iovisor/bcc/blob/master/INSTALL.md#install-and-compile-bcc-1
RUN git clone --depth 1 --branch ${BCC_VERSION} https://github.com/iovisor/bcc.git &&\
    mkdir bcc/build; cd bcc/build  &&\
    cmake .. &&\
    make -j$(nproc) &&\
    make install &&\
    cmake -DPYTHON_CMD=python3 .. # build python3 binding &&\
    pushd src/python/ &&\
    make &&\
    make install &&\
    popd

# for convenience
RUN apt-get update && apt-get install curl -y
RUN curl https://raw.githubusercontent.com/brendangregg/FlameGraph/master/flamegraph.pl -o /usr/share/bcc/tools/flamegraph.pl && chmod +x /usr/share/bcc/tools/flamegraph.pl
