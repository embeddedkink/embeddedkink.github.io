# Lockbox

[back](./)

GitHub repositories:

- [control](https://github.com/embeddedkink/lockbox-controller)
- [enclosure](https://github.com/embeddedkink/lockbox-enclosure)
- [firmware](https://github.com/embeddedkink/lockbox-firmware)

## About

This project aims to create a secure lockbox that can be connected to online keyholding services with minimal effort. With a companion app on a desktop, locking up is as easy as running one single command, and uploading the resulting .txt or .png file.
Usage of the box is fully private and neither the box nor the controlling software pings out to remote servers. Privacy is a right we take very seriously.

The project has been designed to be as easy to set up as possible. Off the shelf components like the NodeMCU Amica and an SG90 servo have been chosen for their wide availability. The rest is 3d printed for easy customization.

## Selling points

- Secure. No way to break into the box without physically destroying it
- Safe. Is the emergency bigger than the cost of replacing the box? Just force the lid off. (This does destroy the box!)
- Cheap. Only one actuator and no real time clock necessary
- Compatible with all locks based on small physical keys (larger key compatibility coming soon!)
- Based on common off-the-shelf (COTS) and 3d printed parts
- Fully local system, no dependency on the cloud and no telemetry is collected

## Usage

Connect power to the microcontroller. Put the key into the empty partition of the lockbox. Put the lid onto the box. Lock using the controller, send the password away to your platform of choice (Emlalock is known to accept `.txt` files), and delete it permanently on you local machine. The box can now be safely turned off. It only needs to be turned on again when you have the password. For details on how to use the controller, read [the readme](https://github.com/embeddedkink/lockbox-controller)

### Recovering

If you had to abort a session, the electronics can be reset and used in a new box. This can be done by simply connecting the usb port on the microcontroller, listening on the UART (`picocom -b 9600 /dev/ttyUSB0` or with the Arduino IDE) and pressing the RESET button on the microcontroller. It will now send data about its status and the password. Use this password with the control software to unlock like normal.

## Technical details

[Assembly guide](./lockbox-assembly-guide.md)

### A note on updates

The box can be updated manually but will not be seeking for the latest updates automatically. Updating the box is not hard, but requires some technical steps. An update utility is in the works. Until then, the version of the control software that matches the firmware of your lock box will be accessible on GitHub.

### Power

The box has been measured to draw 0.4 amps at 5 volts with the servo stalled. This should be handled by most modern USB devices. Do note that its behaviour is not guaranteed to be in spec so the use of a quality USB power supply is recommended.
Note that some servos may not perform identically to ours, even if they're marketed as 9g SG90.

The box allows dupont cables to come out of the bottom. You can power it with a female USB micro-b to dupont breakout board along with 2 dupont female to female wires; solder your own USB to dupont cable; or even 3d print a USB to dupont adapter.

### Compatibility

Early versions of the box were controlled with a TCP connection. This is no longer recommended. Use the latest version of the MCU firmware along with the latest version of the control software. Each can be found in their own repository.
Boxes and lids come with their commit hash on the top and bottom. eae25c is a good minimal box but relies on a specially printed locking cam. Later boxes like acaa41 use a horn that comes with the servo that has then be cut to length. Boxes and lids of the same commit hash are guaranteed to be compatible. Some other boxes and lids may be compatible with each other as well, but this is not documented.
