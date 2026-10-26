# Reaction Wheel Inverted Pendulum

A desktop-scale reaction wheel pendulum that swings itself up from the hanging position and balances upright — designed, modelled, built and controlled from scratch as a solo engineering project.

**Status:** Phase 0 — modelling and simulation (started October 2026)

## What this project covers

- **Modelling:** equations of motion via Euler–Lagrange, linearisation, controllability analysis
- **System identification:** measuring inertia, friction and motor constants on the real hardware
- **Control:** energy-based swing-up + LQR balance, with a mode-switching state machine
- **State estimation:** complementary and Kalman filters on IMU data, validated against a joint encoder
- **Embedded:** field-oriented control (FOC) of a BLDC motor written from scratch in C on an STM32
- **Hardware:** custom KiCad board with current-sensed motor driver

Every phase compares simulation against measurement, with the numbers reported.

## Roadmap

| Phase | Content | Status |
| --- | --- | --- |
| 0 | Modelling and simulation (MATLAB/Simulink) | In progress |
| 1 | Bench setup, encoder reading, FOC, wheel speed loop | Planned |
| 2 | System identification | Planned |
| 3 | State estimation (complementary / Kalman filter) | Planned |
| 4 | Balance control (LQR) | Planned |
| 5 | Swing-up | Planned |
| 6 | Custom PCB with current-loop FOC | Planned |
| 7 | LQR vs. PID comparison, report, video | Planned |

## Hardware (first version)

- STM32 Nucleo-F446RE
- GM4108H-120T gimbal BLDC motor with AS5048A encoder
- DRV8313-based driver (SimpleFOC Mini)
- AS5600 magnetic encoder at the pivot, IMU on the arm
- 24 V DC supply, 2020 aluminium extrusion frame, 3D-printed parts

## Repository layout

```
docs/        derivations, parameter tables, phase notes, figures
model/       Simulink models and MATLAB scripts
firmware/    STM32CubeIDE project
tools/       Python scripts: serial logging, plotting, system identification
hardware/    KiCad project and BOM
mechanical/  CAD parts and STL files
```

## References

- K. J. Åström, K. Furuta, "Swinging up a pendulum by energy control," *Automatica*, 36(2), 2000.
- D. J. Block, K. J. Åström, M. W. Spong, *The Reaction Wheel Pendulum*, Morgan & Claypool, 2007.

## Author

Mehmet Ege Baysal — Mechatronics Engineer
[LinkedIn](https://www.linkedin.com/in/mehmet-ege-baysal-3245b7273)
