FROM debian:stable-slim
LABEL Author="Paul Dreik"
LABEL Description="Generic base for compilation with llvm and cmake. Not minimal, but useful."

# setup future use of llvm repo
ADD https://apt.llvm.org/llvm-snapshot.gpg.key llvm-snapshot.gpg.key
RUN apt-get update && apt-get dist-upgrade -y && apt-get -y install gpg ca-certificates
RUN apt-key add llvm-snapshot.gpg.key && rm llvm-snapshot.gpg.key

# install cmake
RUN gpg --keyserver hkps://keyserver.ubuntu.com --recv-keys 0xcba23971357c2e6590d9efd3ec8fef3a7bfb4eda
ADD https://github.com/Kitware/CMake/releases/download/v3.18.4/cmake-3.18.4-SHA-256.txt .
ADD https://github.com/Kitware/CMake/releases/download/v3.18.4/cmake-3.18.4-SHA-256.txt.asc .
ADD https://github.com/Kitware/CMake/releases/download/v3.18.4/cmake-3.18.4-Linux-x86_64.sh .
RUN gpg --verify cmake-3.18.4-SHA-256.txt.asc cmake-3.18.4-SHA-256.txt
RUN sha256sum --ignore-missing -c cmake-3.18.4-SHA-256.txt
RUN chmod +x cmake-3.18.4-Linux-x86_64.sh && ./cmake-3.18.4-Linux-x86_64.sh --skip-license --prefix=/usr && rm cmake-3.18.4*

# install ninja and make
RUN apt-get install -y ninja-build make

# other useful tools
RUN apt-get install -y git less

