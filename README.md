# BLDC Hat

![IC](https://img.shields.io/badge/IC-DRV8316C-03234B?style=flat-square&logo=stmicroelectronics&logoColor=white)
![PCB](https://img.shields.io/badge/PCB-4--layer%20%C2%B7%2058.75%20%C3%97%2035.5%20mm-2E8B57?style=flat-square)
![EDA](https://img.shields.io/badge/KiCad-314CB0?style=flat-square&logo=kicad&logoColor=white)
![Control: FOC](https://img.shields.io/badge/Control-FOC-7B2CBF?style=flat-square)

A four-layer BLDC motor driver hat built around the TI DRV8316C for the [STM32F405 development module](https://github.com/eggsacc/stm32f405-module). It is intended for six-PWM motor control and field-oriented control experiments.

![BLDC Hat perspective render](assets/pcb-perspective-render.png)

## Hardware

- Three-phase driver with six PWM inputs, three low-side current-sense outputs, SPI configuration/status, and motor-supply voltage sensing.
- Onboard 5 V buck converter with a switch for MCU power, plus power and fault LEDs.
- Four-layer PCB; board revision V1.4.

## Connectors

| Connector | Purpose |
| --- | --- |
| CN1 · XT30 | Motor power input (`VM_IN`) |
| U3 · MR30 | Three motor phases (`U`, `V`, `W`) |
| J2 · 2×10 | Interface to the STM32F405 module |
| J4 · 2×3 | Six PWM inputs (`CH1–3`, `C1N–3N`) |
| J1 · 2×3 | Driver SPI (`CLK`, `CS`, `MI`, `SI`, 3V3, GND) |
| J5 · 1×4 | I²C (`SDA`, `SCL`, 3V3, GND) |
| CN2 · XT30 | Optional motor-power output; marked DNP in the BOM |

With `MCU PWR` on, the hat supplies 5 V to the MCU module. Its [power guidance](https://github.com/eggsacc/stm32f405-module#power) warns against connecting USB and external 5 V at the same time.

## Layout
>L1: Power & signal

![alt text](assets/layout-l1.png)

>L2: GND

![alt text](assets/layout-l2.png)

>L3: GND + PWM signal

![alt text](assets/layout-l3.png)

>L4: GND + signal

![alt text](assets/layout-l4.png)

> Silkscreen
![alt text](assets/silkscreen-layout.png)

>Combined
![alt text](assets/layout-all-layers.png)

The [KiCad project](HatDrive_kicad/) contains the schematic, PCB, and manufacturing files. See the [MCU module README](https://github.com/eggsacc/stm32f405-module) for its pinout.

---

<div align="center">
Designed by <b>@eggsacc</b> · HatDrive V1.4 <br>
Updated 02/10/2026
</div>
