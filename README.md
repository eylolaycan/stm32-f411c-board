## STM32 Sensor Board

This project is a custom PCB design based on an STM32 microcontroller.
It includes USB power input, SWD programming interface, and an onboard MC6470 6-axis sensor (accelerometer + magnetometer).
The goal of this board is to create a compact and reliable platform for motion and orientation sensing experiments.

## Overview

The schematic is organized into several functional sections:

# 1. Power Supply

The board is powered through a USB Type-C connector (5V input).
An adjustable LDO regulator generates the 3.3V rail for the microcontroller and sensors.
A power LED indicates when the board is active.
Proper decoupling capacitors are used to ensure voltage stability.

# 2. Microcontroller Unit (MCU)

The main component is an STM32 microcontroller.
External 8 MHz crystal oscillator ensures stable clock operation.
Decoupling capacitors and VCAP pins are placed according to the STM32 hardware design guidelines.
NRST circuit includes a pull-up resistor and a filtering capacitor for reliable startup.

# 3. Programming and Debug Interface

A standard SWD header is included for firmware upload and debugging.
Signals: SWCLK, SWDIO, NRST, VCC, and GND.
Compatible with ST-Link and similar programmers.

# 4. IMU Sensor (MC6470)

The MC6470 combines a 3-axis accelerometer and a 3-axis magnetometer.
Communication with the MCU is through the I²C bus (SCL and SDA).
Interrupt outputs (INTA, INTM) are connected to GPIO pins.
TM and PM pins are grounded for stability as mentioned in the datasheet.
The sensor has local decoupling capacitors for noise suppression.
Electrical Characteristics
Input Voltage: 5V (via USB)
Operating Voltage: 3.3V
Communication Interface: I²C
Programming Interface: SWD

## Purpose

This board is designed for academic and experimental use. It can be used for projects involving motion sensing, embedded systems development, and sensor data acquisition using STM32.

## Tools Used

Altium Designer: for schematic and PCB design
Git & GitHub: for version control and documentation
STM32CubeIDE: for firmware development

## Gallery
![Top 3D](/Board_3d_Top.png) 
![Schematic](/Schematic.png)
