# riscv docker image

### Build riscv docker image
```bash
docker build -t riscv -f riscv.Dockerfile .
```

### Run riscv docker image
```bash
docker run -d riscv
```

### Connect to riscv docker container
```bash
docker run -d -p 2222:2222 riscv
ssh root@localhost -p 2222

#default username and password is "root"
```

# References
1. https://github.com/DavidBurela/riscv-emulator-docker-image
2. https://risc-v-getting-started-guide.readthedocs.io/en/latest/linux-qemu.html
3. https://blog.davidburela.com/2020/11/15/emulating-risc-v-debian-on-wsl2/