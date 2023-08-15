# Manual flashing

## Installing

If the web installer fails or you want to make your own changes to the firmware, you can use PlatformIO.

Firstly, install Visual Studio Code and the PlatformIO extension. Not all VSC forks will work as Microsoft is being an ass about plugins while still advertising being open source.

Install Git and clone the repository, or download an archive. It is recommended to use Git as this will make updating the firmware easier.

Open PlatformIO and open the lockbox-firmware project. The default target will be env:nodemcuv2_unofficial. This is probably what you want.

## Firmware

Compile and upload the firmware using PlatformIO. This should be easy to find.

## Filesystem

Build and upload the filesystem image. This option is hidden a bit further away.

If you upload the firmware but not the filesystem, the board will boot but it will encounter an exception after connecting to WiFi.
