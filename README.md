# SDL2 Example

Simple template to get started with [SDL2](https://www.libsdl.org/).

This template uses [cmkr](https://github.com/build-cpp/cmkr) together with [vcpkg](https://github.com/microsoft/vcpkg) for frictionless cross platform dependency management with CMake.

## Building (IDE)

Clone this repository and open it in your favorite IDE with CMake support ([Visual Studio](https://visualstudio.microsoft.com/), [CLion](https://www.jetbrains.com/clion/), [Qt Creator](https://www.qt.io/product/development-tools)). Everything should work out of the box.

## Building (command line)

```sh
cmake -B build
cmake --build build
```

## cmake.toml

Under the hood cmkr generates the `CMakeLists.txt` required to build this project from the `cmake.toml` file:

```toml
# Reference: https://build-cpp.github.io/cmkr/cmake-toml
[project]
name = "cmkr-sdl"

[vcpkg]
version = "2023.01.09"
packages = ["sdl2"]

[find-package.SDL2]

[target.cmkr-sdl]
type = "executable"
sources = ["src/cmkr-sdl/main.cpp"]
compile-features = ["cxx_std_11"]
link-libraries = ["SDL2::SDL2", "SDL2::SDL2main"]
```