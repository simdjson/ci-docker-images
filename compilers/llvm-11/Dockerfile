FROM pauldreik/llvm-generic
LABEL Author="Paul Dreik"
LABEL Description="Provide a well defined C++ environment using clang 11. Not minimal, but useful."

RUN echo "deb https://apt.llvm.org/buster/ llvm-toolchain-buster-11 main" >>/etc/apt/sources.list.d/llvm-11.list
RUN apt-get update
RUN apt-get install -y libllvm-11-ocaml-dev libllvm11 llvm-11 llvm-11-dev llvm-11-doc llvm-11-examples llvm-11-runtime
RUN apt-get install -y clang-11 clang-tools-11 clang-11-doc libclang-common-11-dev libclang-11-dev libclang1-11 clang-format-11 python3-clang-11 clangd-11
RUN apt-get install -y libfuzzer-11-dev
RUN apt-get install -y lldb-11
RUN apt-get install -y lld-11
RUN apt-get install -y libc++-11-dev libc++abi-11-dev
RUN apt-get install -y libomp-11-dev

