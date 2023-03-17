# Auto Mouse

## Description

This is a minimal example of how to build a mouse with the TinyUSB library for the Raspberry Pico.

## How to build

First of all, if not already done, you have to clone the repository of the pico sdk somewhere on your system. It is available at https://github.com/raspberrypi/pico-sdk.git .

```shell
git clone https://github.com/raspberrypi/pico-sdk.git
```

The pico sdk repository also provides a README.txt file with everything necessary in order to compile a raspberry pico project, but in short simply run :

```shell
sudo apt install cmake gcc-arm-none-eabi libnewlib-arm-none-eabi libstdc++-arm-none-eabi-newlib
```

You are now able to compile this project by running the following lines (change `/your/sdk/path` for your actual sdk path) :

```shell
mkdir build
cd build
cmake -DPICO_SDK_PATH=/your/sdk/path ..
make
```

If you have a standard Ubuntu distribution (this is probably also true for other distributions), the pico should mount under `/media/user/RPI-RP2` (replace `user` by your actual login).
So if you press the bootsel button, plug the pico, and release the button, you can load the executable with :

```shell
cp auto_mouse.uf2 /media/user/RPI-RP2/
```