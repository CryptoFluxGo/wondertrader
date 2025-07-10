# upgrade to 20.04
FROM ubuntu:20.04
LABEL email=fuyy2008@gmail.com

# non interactive mode
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    git \
    gcc-8 \
    g++-8 \
    cmake \
    sudo \
    p7zip-full && \
    rm -rf /var/lib/apt/lists/*

# add debugger
RUN apt-get update && apt-get install -y gdb && \
    rm -rf /var/lib/apt/lists/*


# 将gcc符号链接到gcc8
RUN rm /usr/bin/gcc && \
    ln -s /usr/bin/gcc-8 /usr/bin/gcc && \
    ln -s /usr/bin/g++-8 /usr/bin/g++

# 添加预编译依赖库，并解压
ADD mydeps_gcc8.4.0.7z /home
RUN cd /home && 7za x mydeps_gcc8.4.0.7z


WORKDIR /home/wondertrader/

