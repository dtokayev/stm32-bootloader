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

```bash
# Clone the repo
git clone https://github.com/dtokayev/stm32-bootloader.git
cd stm32-bootloader
git submodule init
git submodule update

# Build libopencm33
cd libopencm3
make
cd ..

# Build bootloader firmware
cd bootloader
make
cd ..

# Build main application firmware
cd app
make
cd ..
```

## Flashing

Connect board to the computer and run

```bash
cd app
make
st-flash write firmware.bin 0x8000000
```

## Connecting to serial port

Run `cu -l /dev/ttyACM0 -s 115200`. You may need to change `/dev/ttyACM0` to another path assigned by your OS.

## Debugging

```bash
# Connect board to computer

# Start debugging server
st-util

# Start GDB from a separate terminal.
# Replace 'example_file.elf' with desired
# firmware file (e.g. app/firmware.elf or
# bootloader/bootloader.elf)
arm-none-eabi-gdb example_file.elf

# Connect GDB to debugging server
(gdb) target extended localhost:4242

# Load the program
(gdb) load

# Start execution with breakpoint
# at first line of code
(gdb) start
```

## Credits

I want to thank [Low Byte Productions Youtube channel](https://www.youtube.com/channel/UC56l7uZA209tlPTVOJiJ8Tw) for his [Bare Metal Programming Playlist](https://youtube.com/playlist?list=PLP29wDx6QmW7HaCrRydOnxcy8QmW0SNdQ) which helped me to start with embedded programming.
