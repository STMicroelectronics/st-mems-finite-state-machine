## 1 - Introduction

This Finite State Machine (FSM) example enables the *High-g Automatic Toggle* suitable for dynamically turning on the high-g sensor when a high-g event is likely to occur.

The FSM processes data coming from the low-g accelerometer, configured at 16g, 480 Hz.

Configurable parameters:

- Threshold 1: free-fall start threshold (default 0.2g)
- Threshold 2: saturation start threshold (default 13g)
- Timer 1: minimum time with high-g sensor enabled (default 2 seconds)
- SETR argument (ODR_XL_HG_[2:0] value): ODR of high-g sensor (default 480Hz)

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

Any orientation.

## 3 - Finite State Machine output values

- FSM_OUTS1 register values
  - 01h = Saturation event, high-g sensor ON
  - 02h = Free-fall event, high-g sensor ON
  - FFh = No event, high-g sensor OFF

## 4 - Interrupts

The configuration generates an interrupt on INT1 when moving from a *Saturation event* or *Free-Fall event* condition to a *No event* condition, and vice-versa. Reading the FSM_OUTS1 register allows to determine the new state.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2026 STMicroelectronics**
