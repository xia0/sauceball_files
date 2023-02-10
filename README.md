# sauceball_files
A project for upcycling ps/2 optical mice into trackballs.
![sauceball DIY trackball](https://i.imgur.com/h5vI6Rqh.jpg)

## Required parts
* 3D printed shells
* 3D printed mounting bracket and spacers (Will need to be custom made for your specific mouse PCB)
* 1 × 52.5 mm billiards ball (avoid red)
* 1 × PS/2 compatible optical mouse
* 1 × MCU e.g.:
    * Teensy 2.0 - limited to USB Mini-B port
    * Arduino Pro Micro - [pin D5 needs to be exposed](https://golem.hu/guide/pro-micro-upgrade/)
* 4 × keyswitches
* 2 × 1.25u keycap
* 2 x 1u keycap
* 4 × diode [required for hand wiring](https://github.com/qmk/qmk_firmware/blob/master/docs/hand_wire.md)
* 2 × 4K7 Ohm resistor [required to hooking up PS/2 mouse to MCU](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_ps2_mouse.md)
* 3 × CY-8H ball transfer unit
* 6 × M3*3 mm x 5 mm OD threaded insert
* 6 × M3*6 mm bolts
* 3 mm cable ties to secure MCU to bottom shell