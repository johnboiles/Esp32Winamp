# Winamp on ESP32

I thought @moononournation's [Winamp on ESP32](https://www.youtube.com/watch?v=CRNgICzIGy0) video and [Instructable](https://www.instructables.com/Design-Music-Player-UI-With-LVGL/) was incredible, and I had to have one, but the [original repo](https://github.com/moononournation/LVGL_Music_Player) didn't have any instructions on how to build it. So in this repo I've set it up to build with ESP-IDF 4.4.4.

## Compiling

You'll need ESP-IDF 4.4.4 which as 16 June 2023 is the highest version of ESP-IDF that works out of the box with [arduino-esp32](https://github.com/espressif/arduino-esp32). Installation instructions are [here](https://docs.espressif.com/projects/esp-idf/en/v4.4.4/esp32/get-started/index.html#step-1-install-prerequisites). It's typically something like:

```bash
mkdir -p ~/esp
cd ~/esp
git clone -b v4.4.4 --recursive https://github.com/espressif/esp-idf.git
```

Now from this repo, make sure you have the submodules:

```bash
git submodule update --init --recursive
```

Then build with:

```bash
. $HOME/esp/esp-idf/export.sh
idf.py set-target esp32s3
idf.py build flash monitor
```

This should upload and return logs for any connected EESP32.

## TODO:

* I only have the 480x320 boards (SC-01 Plus) so I haven't tested the other boards. I haven't put in the effort to make the CMakeLists.txt have an option for the different boards, but that's probably not too hard.
