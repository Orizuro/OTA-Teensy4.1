Based on Teensy 2.0, LC, 3.x, 4.x core libraries for Arduino, and FlasherX.\
Teensyduino -> https://github.com/PaulStoffregen/cores \
FlasherX -> https://github.com/joepasquariello/FlasherX \
Currently how it works:\
The update method is to transfer the new firmware to the Teensy via Serial, buffer the new firmware in unused flash, erase the existing firmware, copy the new firmware from the buffer to the flash base address, erase the buffer, and reboot to run the new firmware.

The final goal:
Splitting the Flash in two parts, like that having two firmwares available on the board.
The update method is to transfer the new firmware to the Teensy via Serial and Wireless, buffer the new firmware,copy the new firmware from the buffer to the half of the flash that currently is not in use, reboot to run the new firmware.
Have a means to change the desired firmware to run.