# Crazy Street: Automatic Street Light Control System (8051)

An energy-saving street light controller built around the AT89C51 (8051) microcontroller. IR sensors detect vehicles on the road, and the corresponding LED street lights switch on while a vehicle is present and switch off after it passes. The circuit was simulated in Proteus, prototyped on a breadboard, and then built on a custom PCB designed in EasyEDA.

## Project Details

| Field      | Details                                                          |
|------------|------------------------------------------------------------------|
| Course     | Mini Project III (ET 391), B.Tech Semester V                     |
| Department | Electronics and Telecommunication Engineering                    |
| College    | Pillai College of Engineering (Autonomous), University of Mumbai |
| Year       | A.Y. 2025-26                                                     |
| Guide      | Dr. Ameet M. Mehta                                               |

## Team

| Roll No. | Name              |
|----------|-------------------|
| 545      | Yash Rangra       |
| 551      | Om Shinde         |
| 558      | Govind Vaidya     |
| 561      | Aditi Vishwakarma |

## Problem and Motivation

Many street lights stay on even when roads are empty, which wastes electricity and shortens lamp life. This project switches lights on only when a vehicle is detected, as a low-cost model for energy-efficient smart city lighting.

## Objectives

- Design an automatic street light control system using the 8051 microcontroller.
- Detect vehicle movement with IR sensors for automatic lighting control.
- Simulate the circuit in Proteus.
- Design and fabricate the system on a PCB for stability and reliability.
- Build practical skills in microcontroller programming and automation.

## Features

- Automatic ON/OFF control of street lights based on vehicle presence.
- IR sensor modules with digital output (logic 0 when a vehicle is detected).
- All lights stay OFF at power-on until a vehicle is detected.
- Delay logic to stabilise sensor response and avoid false triggering.
- Compact custom PCB with connector headers for sensors, LEDs and power.
- Simulation in Proteus before hardware implementation.

## Components

| Component                | Role                                                    |
|--------------------------|---------------------------------------------------------|
| AT89C51 (8051)           | Main control unit                                       |
| IR sensor modules        | Vehicle detection                                       |
| LEDs                     | Street light outputs                                    |
| Resistors                | Current limiting for LEDs, 10k pull-down for sensors    |
| Capacitor 10 uF          | Reset circuit                                           |
| Capacitors 33 pF (x2)    | Crystal oscillator stability                            |
| 12 MHz crystal           | Clock source                                            |
| 7805 regulator           | Regulated 5 V supply                                    |
| Push button              | Reset                                                   |
| Connector headers        | Sensor, LED and power connections on the PCB            |

### Software Tools

| Tool                  | Role                                       |
|-----------------------|--------------------------------------------|
| Keil uVision          | Writing and compiling the program          |
| Proteus Design Suite  | Circuit simulation and testing             |
| Flash Magic           | Programming the HEX file into the AT89C51  |
| EasyEDA               | Schematic and PCB design                   |

## Working

1. On power-up, the microcontroller initialises its ports and all street lights are OFF.
2. The IR sensors continuously monitor the road. When a vehicle enters the detection range, the sensor output goes LOW.
3. The microcontroller reads the sensor input on Port 1 and drives the corresponding LED HIGH, turning that street light ON.
4. When the vehicle moves away, the sensor output returns HIGH and, after a short delay, the LED is switched OFF.
5. The loop repeats continuously.

| Vehicle Detection | Sensor Output | LED Status |
|-------------------|---------------|------------|
| No vehicle        | Logic 1       | OFF        |
| Vehicle detected  | Logic 0       | ON         |
| Vehicle moves away| Logic 1       | OFF        |

## Testing and Results

Simulation and hardware tests confirmed that the lights turn ON only when a vehicle is detected and turn OFF shortly after it leaves.

| Parameter               | Observation                                   |
|-------------------------|-----------------------------------------------|
| Response time           | Under 50 ms after vehicle detection           |
| Operating voltage       | 4.8 V to 5.2 V                                |
| Power consumption       | About 200 mW per LED                          |
| Ambient light tolerance | Stable under indoor and outdoor lighting      |
| Reliability             | Ran continuously for several hours without faults |

### Issues Fixed During Development

| Issue                      | Cause                          | Solution                              |
|----------------------------|--------------------------------|---------------------------------------|
| Sensor not detecting       | Improper alignment or distance | Adjusted sensor angle and range       |
| LED not glowing            | Loose wire or damaged LED      | Replaced component, rechecked wiring  |
| Flickering output          | Power instability              | Added decoupling capacitor            |
| False triggering           | Ambient light interference     | Used shielded IR sensor module        |

## Applications

- Smart city and highway street lighting
- Motion-based lighting in parking areas
- Industrial zones and residential complexes
- Educational demonstration of sensor interfacing and automation

## Future Scope

- Wireless or IoT-based monitoring and control of street lights
- Ambient light sensing so lights operate only at night
- Dimming instead of full ON/OFF switching
- Vehicle counting and data logging
