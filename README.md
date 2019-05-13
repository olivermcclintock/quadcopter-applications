# Quadcopter-Applications
Quadcopter &amp; Drone Systems with Engineering Applications

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
- RF controller (Arduino, a program to control our beloved drone that won't crash it)
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
