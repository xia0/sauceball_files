# sauceball
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

## Instructions
1. Verify that your mouse is ps/2 compatible. Sometimes a USB mouse will be ps/2 compatible but it will not be indicated. The easiest way to check this is by using a green ps/2 to USB adapter. Remember, your computer will have to be restarted for it to recognise a ps/2 device.
2. Desolder the microswitches and rotary encoders to create more space.
3. Mount your PCB to the case to verify that you can get it at the correct position to track your ball accurately. You will need to make a custom mount (instructions below). You will most likely need to play with the height and position using the slotted holes and spacers.
4. Wire everything up using these instructions: [handwiring](https://github.com/qmk/qmk_firmware/blob/master/docs/hand_wire.md) and [ps/2 support](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_ps2_mouse.md) 

## Making your PCB mount
![ps/2 mouse pcb rf-801-32](https://i.imgur.com/pdtQHGd.jpg)
Get a high quality scan of your PCB so you can more easily design your mount around its holes and edges.
![fusion 360 calibrate tool](https://i.imgur.com/FOr35y8.png)
Use the calibrate tool to get your scan at the correct size.
![example of a mounting plate sketch](https://i.imgur.com/Ds6hh3e.png)
Place your PCB canvas so that the optical sensor is slightly below the centre point. I've found they tend to track the ball better in this position. Design your mount with slots so that you can adjust the position of the PCB until you get good focus. You will also need to print some M3 spacers to get your sensor at the optimum height. There is a bit of trial and error to get this right.