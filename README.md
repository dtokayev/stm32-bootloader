# STM32F401RE Bare Metal Programming

This repository hosts code that runs on bare metal on STM32F401RE chip.

## Setup

Install dependencies:

* `arm-none-eabi`
* `git`
* `make`
* `stlink-tools`

Run these commands:

    git clone --recurse-submodules https://github.com/dtokayev/stm32-bootloader.git
    cd stm32-bootloader/libopencm3
    make

## Firmware compilation and flashing

Connect board to the computer and run these commands from root directory:

    cd app/
    make
    st-flash write firmware.bin 0x8000000
