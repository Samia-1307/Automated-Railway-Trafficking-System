# Automated Railway Trafficking System

## Overview
This repository contains the design, simulation, and hardware implementation of an Automated Railway Trafficking System. Developed as a final project for the EEE 304 Digital Electronics Laboratory (January 2024) at the Bangladesh University of Engineering and Technology (BUET). The system optimizes traffic light control across multiple railway lines using real-time sensor data, dynamically generating Red, Yellow, and Green light outputs to ensure efficient train flow and eliminate line conflicts. 

## System Architecture
* **FSM Design:** The traffic control logic is governed by a 10-state Moore Finite State Machine (FSM). 
* **State Encoding:** The 10 states are encoded into a 4-bit binary format (S1, S2, S3, S4) for efficient hardware realization.
* **Inputs:** Three infrared (IR) sensors act as object detectors (L1, L2, L3) to track the real-time presence and motion of trains across three distinct railway tracks.
* **Outputs:** The FSM controls three independent traffic light modules. Each module outputs a Green (immediate departure clearance), Yellow (next in line for departure), or Red (stationary/stop) signal corresponding to its respective track.
* **Traffic Strategy:** The system autonomously manages line priority using a First-Come-First-Serve principle to minimize operational delays.

## Simulation and Implementation
* **Logic Minimization:** The next state and output logic expressions were derived using K-maps from truth tables and implemented in Verilog to generate a minimized cost circuit.
* **Simulation:** The entire circuit design, including the next state and output logic components, was rigorously simulated and validated using Proteus.
* **Hardware Assembly:** The physical prototype was constructed on breadboards utilizing 46 standard logic Integrated Circuits (ICs). The IC inventory includes 74LS08, 74LS11, 74LS21, 74LS30, 4072, 4078, 74LS04, 74LS32, 4075, and 74LS175 chips.
* **Clock Generation:** A 555 timer IC, powered by an independent 9V battery, serves as the clock pulse generator to maintain strict timing and synchronization.
* **Power Supply:** Due to the high power demands of the flip-flops, the main logic circuit is powered by a stable 5V, 200mA mobile charger connected to a standard 220V AC line.

