# Crazy Street: Adaptive Traffic Signal Controller (8051)

A traffic signal controller built around the 8051 microcontroller. It uses an IR sensor array to detect vehicles at each lane in real time and controls the signals accordingly. The signal logic is written in 8051 Assembly language, and the circuit was designed and fabricated as a custom PCB.

## Overview

Fixed-timer traffic signals give green time to lanes with no vehicles while busy lanes wait. Crazy Street addresses this by sensing vehicle presence at every lane and letting the microcontroller decide the signal output based on live detection data.

## Features

- Real-time vehicle detection at each lane using an IR sensor array.
- Traffic signal control driven by the detection inputs.
- Signal logic programmed entirely in 8051 Assembly language.
- Custom PCB designed and fabricated for the 8051 based controller.

## Tech Stack

| Area            | Details                                  |
|-----------------|------------------------------------------|
| Microcontroller | 8051                                     |
| Language        | 8051 Assembly                            |
| Sensing         | IR sensor array (one sensor set per lane)|
| Hardware        | Custom designed and fabricated PCB       |

## Working

1. IR sensors at each lane continuously monitor for vehicle presence.
2. The 8051 reads the sensor inputs through its I/O ports.
3. The Assembly program evaluates the lane status and decides which signals to switch.
4. The traffic signal outputs are updated based on that decision.
5. The cycle repeats continuously, so the signals follow the current traffic.

## Future Scope

- Priority handling for emergency vehicles
- Pedestrian crossing support
- Adjustable signal timing per lane
- Vehicle count logging
