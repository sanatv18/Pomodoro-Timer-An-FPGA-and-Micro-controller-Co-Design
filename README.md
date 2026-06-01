# FPGA-Based Pomodoro Timer: An FPGA and Microcontroller Co-Design

## Overview

This project presents an FPGA-based Pomodoro Timer implemented on the **Vicharak Shrike Lite** development platform. The system combines an **SLG47910V FPGA** and an **RP2040 microcontroller** to create a productivity timer based on the Pomodoro technique.

The FPGA performs deterministic timing operations and state-machine control, while the RP2040 receives timer data through UART communication and displays the information on an SH1106 OLED display. Visual and haptic feedback is provided using LEDs, a buzzer, and a vibration motor.

---

## Features

* FPGA-based countdown timer using Verilog RTL
* Pomodoro work and break cycle management
* UART communication between FPGA and RP2040
* Real-time timer display on SH1106 OLED
* Green and Red LED status indicators
* Buzzer and vibration motor alerts
* FPGA–MCU co-design architecture
* Automatic FPGA bitstream loading using LittleFS
* Low-cost and portable implementation

---

## Hardware Components

* Vicharak Shrike Lite Development Board
* Renesas SLG47910V FPGA
* RP2040 Microcontroller
* SH1106 OLED Display (128×64)
* Vibration Motor Module
* Passive Buzzer
* Green LED
* Red LED
* Perfboard and Supporting Components

---

## Software & Tools

* Renesas Go Configure Software Hub
* Intel Quartus Prime
* Arduino IDE
* Shrike Library
* Adafruit SH110X Library
* Adafruit GFX Library
* LittleFS
* Verilog HDL

---

## System Architecture

```text
              ┌─────────────────┐
              │ Renesas FPGA    │
              │ (Timer Logic)   │
              └───────┬─────────┘
                      │ UART
                      ▼
              ┌─────────────────┐
              │ RP2040 MCU      │
              │ Display Control │
              └───────┬─────────┘
                      │ I2C
                      ▼
              ┌─────────────────┐
              │ OLED Display    │
              └─────────────────┘

        FPGA Outputs
        ├── Green LED
        ├── Red LED
        ├── Buzzer
        └── Vibration Motor
```

---

## Working Principle

1. The FPGA initializes a countdown timer.
2. A clock divider generates one-second timing intervals.
3. The timer alternates between:

   * Work Mode (25 minutes)
   * Break Mode (30 seconds for demonstration)
4. Timer values are transmitted to the RP2040 using UART.
5. The RP2040 receives and formats the timer data.
6. Current time is displayed on the OLED screen.
7. LEDs indicate the active state:

   * Green LED → Work Mode
   * Red LED → Break Mode
8. The buzzer and vibration motor provide user alerts during state transitions.

---

## Project Objectives

* Design a Pomodoro Timer using FPGA technology
* Implement timer control logic in Verilog RTL
* Establish UART communication between FPGA and RP2040
* Display timer information on an OLED display
* Provide visual and haptic feedback
* Demonstrate FPGA and MCU co-design principles

---

## Results

### Achievements

* Successful implementation of Pomodoro timer logic on FPGA
* Reliable UART communication with RP2040
* Real-time OLED display updates
* Correct work/break state transitions
* Functional LED, buzzer, and vibration motor alerts
* Successful synthesis, simulation, and hardware validation

### Timing Performance

* Positive Setup Slack
* Positive Hold Slack
* Stable FPGA operation
* Successful RTL implementation and testing

---

## Repository Structure

```text
├── FPGA_Code/
│   ├── pomodoro_timer.v
│   ├── uart_tx.v
│   └── testbench.v
│
├── MCU_Code/
│   └── rp2040_display.ino
│
├── Images/
│   ├── block_diagram.png
│   ├── rtl_view.png
│   └── hardware_setup.jpg
│
├── Report/
│   └── FPGA_Pomodoro_Timer_Report.pdf
│
└── README.md
```

---

## Applications

* Productivity and Time Management
* FPGA Learning Projects
* Embedded Systems Education
* FPGA–MCU Communication Demonstrations
* Digital System Design Experiments

---

## Future Improvements

* Custom PCB implementation
* Rechargeable battery integration
* Configurable timer durations through OLED menu
* Enhanced UART communication protocol
* PWM-based buzzer tones
* Graphical OLED user interface
* Multiple Pomodoro profiles

---

## Team Members

* Rohan Venkataraman (24BEC0174)
* Joseph Justin (24BEC0227)
* Sanat Vasisht (24BEC0411)
* Varun Shankar (24BEC0230)

Department of Electronics and Communication Engineering

Vellore Institute of Technology (VIT)

---

## License

This project is developed for academic and educational purposes.
