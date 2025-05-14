# pinebuds-hmpthcs
notes on flashing and such

Trying to do this without docker..


## Bestool
Tool to read and write data to/from the pinebuds.

```
$ git clone --recursive https://github.com/ralim/bestool
$ cd bestool/bestool
$ cargo build --release
```

Need serial port drivers I think. Already had these on my system--circle back later to figure out and document how to set up from nil.


## Firmware build

```
$ git clone https://github.com/pine64/openpinebuds
$ cd openpinebuds

# Need toolchain. For building on x86_64:
$ mkdir src
$ curl https://armkeil.blob.core.windows.net/developer/Files/downloads/gnu-rm/9-2019q4/gcc-arm-none-eabi-9-2019-q4-major-x86_64-linux.tar.bz2 | tar -xj -C src/.

# Initial try (errors):
$ PATH="${PATH}:src/gcc-arm-none-eabi-9-2019-q4-major/bin" make -j "$(nproc)" T=open_source DEBUG=1

make[1]: hostname: No such file or directory
  LDS     _best1000.lds
/bin/sh: line 1: arm-none-eabi-gcc: command not found
[...]
```
