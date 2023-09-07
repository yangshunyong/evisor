# Virtual serial console test app

## How to build

### Rasberry Pi4

```shell
mkdir build && cd build
cmake .. -DCMAKE_TOOLCHAIN_FILE=../../../cmake/cross-toolchain-gcc-aarch64.cmake -DBOARD=raspi4
cmake --build .
```

### QEMU

```shell
mkdir build && cd build
cmake .. -DCMAKE_TOOLCHAIN_FILE=../../../cmake/cross-toolchain-gcc-aarch64.cmake -DBOARD=qemu
cmake --build .
cp serial.bin qemu_rom.bin
xxd -i qemu_rom.bin > ../qemu_rom.c
```
