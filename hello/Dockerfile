FROM debian:unstable-slim AS build
WORKDIR /opt
RUN apt update -y && apt install binutils nasm -y
COPY hola.s .
RUN riscv64-linux-gnu-as -march=rv64imac -o hola.o hola.s
RUN riscv64-linux-gnu-ld -o hola hola.o

FROM scratch
COPY --from=build /opt/hola /
CMD ["/hola"]