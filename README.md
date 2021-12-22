# stm32_cmake_example
stm32使用cmake构建工程的示例

**0.软件包需要下载**

- stm32cubemx

- [官网cmake](https://cmake.org/)

```
$ cmake --version
```

- [gcc-arm-none-eabi工具链](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)

```
$ arm-none-eabi-gcc --version
```

- [tdm-gcc编译器](https://jmeubank.github.io/tdm-gcc/)

```
 mingw32-make.exe --version
```

**1.stm32cubemx自生成makefile使用**

工程目录下

```
$ mingw32-make.exe -j
```

清除编译

```
$ mingw32-make.exe clean
```

**2.cmake生成makefile**

```
$ mkdir cmake-build-debug
$ cd cmake-build-debug/
$ cmake -G "MinGW Makefiles" -D CMAKE_TOOLCHAIN_FILE=../arm-none-eabi-gcc.cmake -DCMAKE_BUILD_TYPE=Debug ..
$ mingw32-make.exe -j
```

如果要重新使用makefile生成，删除cmake-build-debug下所有文件
