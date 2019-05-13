# Quadcopter-Applications
Quadcopter &amp; Drone Systems with Practical Applications

The MyDearDrone Quadcopter is our major project. Our design utilizes an ARM Cortext-M3 as its MCU via Flymaple, a custom control board. At the top level is a Linux device (probably a router) used for high-level computing and tasks such as camera control and GPS/IRS navigation. 
## Main Roadmap
###### System Diagram
This is a simple roadmap intended to give a basic understanding of the project's history for anyone who wants to follow us or contribute. 
- Project established
- Build Flymaple prototype
- Motor controls by PWM
- Read data by I2C
- PPM module (pulse-position modulation)
- Manual flight (controlled by RF & remote control)
- Simple self-balance automation (convert unit sensor values to right unit formats, filtering values, and process values)
- RF controller (Arduino, a program to control our [best drone](https://mydeardrone.com/) that won't crash it)
- PC or smartphone sensor control
- W-Fi gateway, and advanced automation protocols
- Advanced self-balancing (through some kind of serial interface)
- Simple Android/iOS or PC controller
###### Copter Controller Timeline
- Sensor test
- Motor control
- Simple self-balancing
- Autopilot for takeoff
- Autopilot for landing
###### RF Controller Timeline
- PPM remote control
- Remote control based on Arduino
- Remote control combined with motor control
- Smartphone control App
###### Wi-Fi Router
- OpenWrt customization
- TP-Link WR703N video driver
- Router control method
- Combined Wi-Fi router with others' models
## About Flymaple
The Flymaple is our Quadcopter controller, based on Maple Project. It uses an STM32F103RET6 (ARM Cortex-M3) as the main MCU.
###### Features
- 72MHz STM32F103RET6 ARM Cotex-M3 microcontroller (Based on Maple RET6)
- 64KB SRAM
- 512KB FLASH ROM
- ITG3205 3-Axis gyroscope
- ADXL345 3-Axis accelerometer
- HMC5883 3-Axis compass
- BMP085 Barometer
- 3x 6-Channel GPIO, used to control 6-channel ESC/Servo
- 3x 8-Channel GPIO, used to capture RC receiver output
- 2x USART (serial) ports ready for XBee and GPS devices
- 2x I2C interfaces ready for ultrasonic sensor altimeters
- Arduino Shield compatible female head interface (AREF, GND)
- SWD/JTAG debugger compatible
###### Flymaple Pins
**NOTE: On most ARM chips (including the STM32F103), all pins can be treated as General Input/Output (GPIO), and all pins can have another re-defined function.** 
## Remote Control
###### Joystick
A 4-axis joystick is an attractive alternative to pricey RC controllers – especially for amateur hobbyists. You can easily grab the analog input events via jstest, which is bundled with most current GNU/Linux distributions.
The following is output captured from an Xbox controller that was connected to a PC via a USB converter. 
```
root@horizons:/home/sam# apt-get install joystick
...
...
root@horizons:/home/sam# jstest --event /dev/input/js0
Driver version is 2.1.0.
Joystick (Microsoft X-Box pad v2 (US)) has 8 axes (X, Y, Z, Rx, Ry, Rz, Hat0X, Hat0Y)
and 10 buttons (BtnX, BtnY, BtnZ, BtnTL, BtnTR, BtnTL2, BtnThumbL, BtnThumbR, ?, ?).
Testing ... (interrupt to exit)
...
...
Event: type 2, time 8880328, number 1, value 28171
Event: type 2, time 8880332, number 0, value -9015
Event: type 2, time 8880332, number 1, value 24633
Event: type 2, time 8880336, number 0, value -4443
Event: type 2, time 8930728, number 3, value 15829
Event: type 2, time 8930728, number 4, value 14862
Event: type 2, time 8930732, number 3, value 13078
Event: type 2, time 8930732, number 4, value 10664
Event: type 2, time 9052172, number 2, value -13933
Event: type 2, time 9052172, number 5, value 774
Event: type 2, time 9052176, number 2, value -17030
Event: type 2, time 9052176, number 5, value -4387
...
...
```
Not all joysticks can be correctly monitored by the Linux kernel, so your results may vary.

To give one example, although the kernel of Ubuntu-12.04-x64 correctly interprets the button and pad events of my PlayStation2 controller (connected via a USB converter), it fails to translate the analog axis events of the same controller. 
## What is DCM matrix
DCM stands for direction cosine matrix. It is a method for representing a rotation through euler angles. Other methods exist as well, for example quaternion is one of the other methods.
###### Euler angles
The Euler angles are three angles introduced by Leonhard Euler to describe the orientation of a rigid body.
## Test DCM Code
###### Install the Processing IDE and compile the monitor
- Download the Processing IDE
- Uncompress the package and run processing bash script to activate - the Processing IDE 
- Download the code of orientation filtering monitor
- Compile code with Processing IDE
###### Install the SDK for flymaple and compile the orientation filtering code
- Install the command line SDK for flymaple
- Download the flymaple code
- Compile code with make command in the root directory of the flymaple code
###### Upload the firmware to flymaple
- Connect flymaple to your computer through a micro usb cable
- Upload the firmware with make install command in the root directory of the flymaple code
- The reset button of the flymaple should be pressed immediately after you do make install  
###### Test the orientation filtering firmware for flymaple
- Set the flymaple on a horizontal surface and press the reset button of flymaple
- Open the monitor. You will see a 3 dimension cube having the same posture with flymaple
## Resources useful for our project :

[http://www1.udel.edu/udaily/2015/mar/trembanis-drone-data-030615.html](http://www1.udel.edu/udaily/2015/mar/trembanis-drone-data-030615.html)

[https://www.researchgate.net/figure/A-structure-of-the-drone-model_fig2_251417046](https://www.researchgate.net/figure/A-structure-of-the-drone-model_fig2_251417046)

[https://libguides.wustl.edu/drones4data](https://libguides.wustl.edu/drones4data)
