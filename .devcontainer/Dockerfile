FROM mcr.microsoft.com/devcontainers/base:ubuntu

RUN apt-get update && apt-get install -y \
    build-essential cmake curl file g++-multilib gcc-multilib \
    git libcap-dev libgoogle-perftools-dev libncurses5-dev \
    libsqlite3-dev libtcmalloc-minimal4 python3-pip unzip

RUN apt-get install -y clang-13 llvm-13 llvm-13-dev llvm-13-tools

RUN pip3 install lit wllvm

RUN apt install -y libz3-4 libz3-dev

RUN git clone https://github.com/klee/klee-uclibc.git && \
    cd klee-uclibc && \
    ./configure --make-llvm-lib --with-cc clang-13 --with-llvm-config llvm-config-13 && \
    make -j2 && cd ..