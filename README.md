# STM32F401RE Bare Metal Programming

This repository hosts code that runs on bare metal on STM32F401RE chip.

## Setup

Install dependencies:

* `arm-none-eabi`
* `git`
* `make`
* `python3`
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

## Connecting to serial port

Run `cu -l /dev/ttyACM0 -s 115200`. You may need to change `/dev/ttyACM0` to another path assigned by your OS.

## Credits

I want to thank [Low Byte Productions](https://www.youtube.com/channel/UC56l7uZA209tlPTVOJiJ8Tw) YouTube channel for his [Bare Metal Programming Playlist](https://youtube.com/playlist?list=PLP29wDx6QmW7HaCrRydOnxcy8QmW0SNdQ) which helped me to start with embedded programming.
