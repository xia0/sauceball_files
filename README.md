# sauceball
A project for upcycling old optical mice into trackballs using [QMK](https://github.com/qmk/qmk_firmware) or jfedor2's [hid-remapper](https://github.com/jfedor2/hid-remapper).
![sauceball DIY trackball](https://i.imgur.com/h5vI6Rqh.jpg)

## Shell parts
| QTY | Part |
| --- | --- |
| 1 | 3D printed top shell |
| 1 | 3D printed bottom shell |
| 1 | 3D printed PCB mount (instructions below) |
| 3 | CY-8H ball transfer unit |
| 1 | 52.5 mm billiards ball |
| 6 | Heat-set insert (M3 thread, 3 mm length, 5 mm OD) |
| 6 | 6 mm M3 bolts |
| 2-3 | 3 mm cable ties to secure MCU to bottom shell (or glue, double sided tape...) |
| 4 | Key switches |
| 2 | 1.25u keycap |
| 2 | 1u keycap |

## If using a PS/2 mouse
| QTY | Part |
| --- | --- |
| 1 | PS/2 compatible optical mouse |
| 1 | ATmega32u4 MCU e.g.: <ul><li>Teensy 2.0 - limited to USB Mini-B port</li><li>Arduino Pro Micro - [need to solder to pin D5 - leg of SMD resistor](https://golem.hu/guide/pro-micro-upgrade/)</li></ul> |
| 4 | diode e.g. 1N4148 [required for hand wiring](https://github.com/qmk/qmk_firmware/blob/master/docs/hand_wire.md) |
| 2 | 4K7 Ohm resistor [required to hooking up PS/2 mouse to MCU](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_ps2_mouse.md) |

## If using [hid-remapper](https://github.com/jfedor2/hid-remapper) by jfedor2
| QTY | Part |
| --- | --- |
| 1 | USB compatible mouse |
| 1-2 | RP2040 MCU e.g. Raspberry Pi Pico |
| 1 | male USB plug to suit your Pi Pico |

## Preparation
1. Verify that your mouse is PS/2 compatible if you plan to use QMK. Sometimes a USB mouse will be PS/2 compatible but it will not be indicated. The easiest way to check this is by using a green USB to PS/2 adapter. PS/2 is not hot-swappable. Ignore this step if you intend to use a USB mouse with [hid-remapper](https://github.com/jfedor2/hid-remapper).
2. Turn the mouse upside down and see if it will track your ball. Some mice just do not track spherical objects well.
3. Desolder the microswitches and rotary encoders to allow the PCB to fit.
4. Mount your PCB to the case to verify that you can get it at the correct position to track your ball accurately. You will need to make a custom mount (instructions below). You will most likely need to play with the height and position using the slotted holes and spacers.

## Making your PCB mount
Make a high quality scan of your PCB so you can more easily design your mount around its holes and edges. Use the calibrate tool to get your scan at the correct size.


| Scan | Calibrate tool |
| --- | ---- | 
| ![ps/2 mouse pcb rf-801-32](https://i.imgur.com/pdtQHGdl.jpg) | ![fusion 360 calibrate tool](https://i.imgur.com/FOr35y8.png) |

Place your PCB canvas so that the optical sensor is slightly south of the centre point. I've found they tend to track the ball better in this position. Design your mount with slots so that you can adjust the position of the PCB for good focus. I wouldn't suggest spending too much time on this step because the majority of the model will be hidden by the PCB and fillets will make everything look good anyway. You will also need to print some M3 spacers of varying thickness to get your sensor at the optimum height. There is a bit of trial and error to get this right and every model of mouse is different. You may need to trim the PCB. I have included an example in this repository.

| Sketch | Printed |
| --- | --- |
| ![example of a mounting plate sketch](https://i.imgur.com/Ds6hh3el.png) | ![example of a completed mounting plate](https://i.imgur.com/NaUHWrhl.jpg) |

## Wiring for PS/2 mouse and QMK
Familiarise yourself with the following documentation:
* [handwiring](https://github.com/qmk/qmk_firmware/blob/master/docs/hand_wire.md)
* [ps/2 support](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_ps2_mouse.md#usart-version-idusart-version) using USART

![wiring diagram for sauceball trackball](https://github.com/xia0/sauceball_files/blob/main/images/sauceball_wiring_diagram.PNG)

Alternatively, you can wire the switches straight to the mouse PCB but you won't be able to remap them in firmware.

### QMK Firmware
Pre-compiled firmware included within this repository. Edit the config.h file of the keymap if you need to change the button mapping or if you want to change the mouse sensitivity. Sensitivity is specified as a percentage. 

## Wiring and firmware for USB mouse and jfedor2's [hid-remapper](https://github.com/jfedor2/hid-remapper)
* [See documentation](https://github.com/jfedor2/hid-remapper/blob/master/HARDWARE.md)
