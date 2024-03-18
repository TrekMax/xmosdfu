# XMOS DFU

## Build with Linux

- Install the required packages

```shell
sudo apt install -y cmake ninja-build libusb-1.0-0-dev
```

- Build the project

```shell
cmake -G Ninja -B build
cmake --build build --config Release
```

- Run

```shell
./build/bin/xmosdfu
```

```shell
ninja: no work to do.
➜  xmosdfu git:(main) ✗ ./build/bin/xmosdfu --listdevices
VID = 0x5e3, PID = 0x626, BCDDevice: 0x656
VID = 0x5e3, PID = 0x626, BCDDevice: 0x656
VID = 0x2109, PID = 0x8110, BCDDevice: 0x9105
VID = 0x1d6b, PID = 0x3, BCDDevice: 0x515
VID = 0x30c9, PID = 0x14, BCDDevice: 0x7
VID = 0x17ef, PID = 0x6157, BCDDevice: 0x625
VID = 0x5ac, PID = 0x24f, BCDDevice: 0x112
VID = 0x1a86, PID = 0x55d3, BCDDevice: 0x445
VID = 0x5e3, PID = 0x610, BCDDevice: 0x656
VID = 0x5e3, PID = 0x610, BCDDevice: 0x656
VID = 0x2109, PID = 0x2811, BCDDevice: 0x9100
VID = 0x8087, PID = 0x26, BCDDevice: 0x2
VID = 0x1d6b, PID = 0x2, BCDDevice: 0x515
VID = 0x1d6b, PID = 0x3, BCDDevice: 0x515
VID = 0x1d6b, PID = 0x2, BCDDevice: 0x515
```

