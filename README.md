# Thermal Comfort Monitoring System

## Description
The **Thermal Comfort Monitoring System** is an Arduino-based project designed to regulate temperature and pressure within a building to ensure optimal comfort. The system integrates **temperature and pressure sensors**, a **heater control mechanism**, and an **LCD display** for real-time monitoring. Users can switch between **manual and automatic modes**, allowing either user-defined temperature settings or autonomous regulation based on sensor readings.

## Features
- **Manual and Automatic Modes:** Users can manually set a target temperature or allow the system to regulate heating automatically.
- **Temperature and Pressure Monitoring:** Reads data from sensors and displays it on an LCD screen.
- **Heater Control:** Activates or deactivates a heating unit based on predefined thresholds.
- **Safety Mechanisms:** Prevents overheating and excessive pressure build-up by shutting down actuators under critical conditions.
- **User Interface:** Displays current temperature, mode of operation, and system status on an LCD screen.

## Implementation
This project is implemented using an **Arduino Uno** microcontroller and utilizes **FreeRTOS** for multitasking. The system is structured as independent tasks that communicate and synchronize through queues and semaphores. The following key components are included:

- **Temperature Measurement:** Simulated via a potentiometer connected to an analog pin.
- **Pressure Measurement:** Simulated via a second potentiometer that regulates system pressure.
- **Heater Control:** A digital output (LED) represents the heating element, which is activated based on temperature thresholds.
- **LCD Display:** Displays real-time data using the **LiquidCrystal I2C** library.
- **Mode Switching:** A digital button allows users to toggle between manual and automatic operation.

## System Architecture
The software is organized into distinct tasks:
1. **Task_T (Temperature Measurement):** Reads temperature data and updates shared variables.
2. **Task_P (Pressure Control):** Monitors pressure and activates or deactivates pumps accordingly.
3. **Task_S (LCD Display):** Displays real-time temperature, pressure, and system status.
4. **Task_SW (Mode Switching):** Handles user input to switch between manual and automatic modes.

## Libraries Used
The following Arduino libraries are utilized in this project:
- `Arduino_FreeRTOS.h` - Enables real-time multitasking with FreeRTOS.
- `LiquidCrystal_I2C.h` - Allows interfacing with an LCD screen over I2C.
- `Wire.h` - Supports I2C communication.


