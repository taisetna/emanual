---
layout: archive
lang: en
ref: turtlebot3_specifications
read_time: true
share: true
author_profile: false
permalink: /docs/en/platform/turtlebot3/specifications/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
---

<div style="counter-reset: h1 2"></div>

# [Specifications](#specifications)

![](/assets/images/platform/turtlebot3/hardware/turtlebot3_models.png)

## [Hardware Specifications](#hardware-specifications)

| Items                              | Burger                    | Waffle                    |
|:-----------------------------------|:--------------------------|:--------------------------|
| Maximum translational velocity     | 0.22 m/s                  | 0.26 m/s                  |
| Maximum rotational velocity        | 2.84 rad/s (162.72 deg/s) | 1.82 rad/s (104.27 deg/s) |
| Maximum payload                    | 15kg                      | 30kg                      |
| Size (L x W x H)                   | 138mm x 178mm x 192mm     | 281mm x 306mm x 141mm     |
| Weight (+ SBC + Battery + Sensors) | 1kg                       | 1.8kg                     |
| Threshold of climbing             |<td colspan=2> 10 mm or lower                       </td>|
| Expected operating time            | 2h 30m                    | 2h                        |
| Expected charging time            | <td colspan=2> 2h 30m                               </td>|
| MCU                               | <td colspan=2> 32-bit ARM Cortex®-M7 with FPU (216 MHz, 462 DMIPS)</td>|
| IMU                               | <td colspan=2> Gyroscope 3 Axis<br />Accelerometer 3 Axis<br />Magnetometer 3 Axis</td>|
| Power connectors                  | <td colspan=2> 3.3V / 800mA<br />5V / 4A<br />12V / 1A</td>|
| Expansion pins                    | <td colspan=2> GPIO 18 pins<br />Arduino 32 pin</td>|
| Peripheral                        | <td colspan=2> UART x3, CAN x1, SPI x1, I2C x1, ADC x5, 5pin OLLO x4</td>|
| Dynamixel ports                   | <td colspan=2> RS485 x 3, TTL x 3</td>|
| Audio                             | <td colspan=2> Several programmable beep sequences</td>|
| Programmable LEDs                 | <td colspan=2> User LED x 4</td>|
| Status LEDs                       | <td colspan=2> Board status LED x 1<br />Arduino LED x 1<br />Power LED x 1</td>|
| Buttons and Switches              | <td colspan=2> Push buttons x 2, Reset button x 1, Dip switch x 2</td>|
| Battery                           |<td colspan=2> Lithium polymer 11.1V 1800mAh / 19.98Wh 5C</td>|
| PC connection                     |<td colspan=2> USB</td>|
| Firmware upgrade                  |<td colspan=2> via USB / via JTAG</td>|
| Power adapter (SMPS)              |<td colspan=2> Input : 100-240V, AC 50/60Hz, 1.5A @max<br />Output : 12V DC, 5A</td>|

## [Dimension and Mass](#dimension-and-mass)

### [Data of TurtleBot3 Burger](#data-of-turtlebot3-burger)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_dimension1.png)

### [Data of TurtleBot3 Waffle](#data-of-turtlebot3-waffle)

![](/assets/images/platform/turtlebot3/hardware_setup/turtlebot3_dimension2.png)

## [Components](#components)

### [SBC](#sbc)

Raspberry Pi 3 Model B : https://www.raspberrypi.org/products/raspberry-pi-3-model-b/

Intel® Joule™ : http://ark.intel.com/products/96414/Intel-Joule-570x-Developer-Kit

### [Sensor](#sensor)

360 Laser Distance Sensor LDS-01 : http://turtlebot3.robotis.com/en/latest/appendix_lds.html

Intel® Realsense™ R200 : https://software.intel.com/en-us/RealSense/R200Camera

### [Control Board](#control-board)

OpenCR1.0 : http://turtlebot3.robotis.com/en/latest/appendix_opencr.html

### [Actuator](#actuator)

Dynamixel X series : http://en.robotis.com/index/product.php?cate_code=10121110
