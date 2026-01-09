# Building Volume Control from Source

## Prerequisites

### Windows
- Visual Studio 2022 or later (with C++ workload)
- CMake 3.10+
- Ninja (recommended) or Visual Studio

### Linux

```Shell
sudo apt-get install cmake ninja-build libpulse-dev build-essential
```

### macOS

```Shell
cmake ninja
```

## Build Instructions

### Configure

```Shell
cmake -G "Ninja" -DCMAKE_BUILD_TYPE=Release -B build -S .
```

### Build

```Shell
cmake --build build --config Release
```

### Run

#### Windows

```CMD
.\build\volume.exe
```

#### Linux/macOS

```Shell
./build/volume
```

#### Optional: Install

```Shell
cmake --install build --prefix /usr/local
```