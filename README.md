# XMOSDFU

## Install Dependencies

```shell
sudo apt update
sudo apt install -y build-essential git cmake ninja-build
sudo apt install -y gcc-mingw-w64-x86-64 g++-mingw-w64-x86-64
```

## Build

```shell
cmake -G Ninja -B build && cmake --build build --config Release
```

## Build for Windows

```shell
cmake -G Ninja -B build_win -D WIN_PLATFORM=true && cmake --build build_win --config Release
```
