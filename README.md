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
