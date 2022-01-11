## Minimalist riscv64 docker image for hello world!

## Dockerfile
```bash
FROM debian:unstable-slim AS build
WORKDIR /opt
RUN apt update -y && apt install binutils nasm -y
COPY hola.s .
RUN riscv64-linux-gnu-as -march=rv64imac -o hola.o hola.s
RUN riscv64-linux-gnu-ld -o hola hola.o

FROM scratch
COPY --from=build /opt/hola /
CMD ["/hola"]
```

## Docker Run
```bash
docker run -it koolwithk/hola:riscv64
```

## References : 
1. Installed ubuntu riscv with qemu - https://discourse.ubuntu.com/t/risc-v-on-ubuntu/22450
2. downloaded docker riscv binary from - https://github.com/carlosedp/riscv-bringup
2. https://smist08.wordpress.com/2019/09/07/risc-v-assembly-language-hello-world/