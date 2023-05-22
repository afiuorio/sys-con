# sys-con

#### A Nintendo Switch custom sysmodule for third-party controller support. No man-in-the-middle required! 
###### \[Switch FW 5.0.0+\] [Atmosphère only]

## Description
This sysmodule aims to provide complete functionality for most popular game controllers not supported by Nintendo Switch.
This is a fork I've made from [pseiler fork](https://github.com/pseiler/sys-con), which provides support to several PS3/4 controllers and arcade sticks. The purpose of this fork is to provide a compiled package of the source code here present.

## Install

Grab the latest zip from the [releases page](https://github.com/panzone91/sys-con/releases). Extract it in your SD card and boot/reboot your switch.

## Config

sys-con comes with a config folder located at `sdmc:/config/sys-con/`. It contains options for adjusting stick/trigger deadzone, as well as remapping inputs. For more information, see `example.ini` in the same folder. All changes to the files will be updated in real time.

## Building (For developers)

Don't download the project as ZIP. It doesn't copy the submodules correctly and you will be left with empty folders.

Instead, clone the repository **recursively** using any git client you have. (Git Bash, Git GUI, Github Desktop, etc.)

For building you will need specific versions of compilers and libraries:

- devkitA64 r17
- devkitARM r56
- devkita64-rules
- devkitarm-rules
- libnx commit **[b35d42f](https://github.com/switchbrew/libnx/commit/b35d42faaa60b02662aaaf0702614f6e4afcbbbc)**. Clone the repository, checkout to that commit, and run `make install` to set it up.

Then, after you have setup the DEVKITPRO environment variable, you can open the console inside the project directory and use one of the following commands:

`make -j8`: Builds the project and its dependencies (libstratosphere) and places the resulting files in the output folder (out/). The -j8 means it will create 8 separate threads to speed up the building process. Make it lower if it freezes up your system.

`make clean`: Cleans the project files (but not the dependencies).

`make mrproper`: Cleans the project files and the dependencies.
