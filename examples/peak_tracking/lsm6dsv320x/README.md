## 1 - Introduction

This Finite State Machine (FSM) example enables the *Peak tracking* suitable for detecting high-intensity impacts.

The FSM processes data coming from the high-g accelerometer, configured at 480 Hz.

Configurable parameters:

- Threshold 1: shock start threshold on high-g accelerometer norm signal [hg], default is 0.40 hg (that is 40 g)
- Threshold 2: shock end threshold on high-g accelerometer norm signal [hg], default is 0.39 hg (that is 39 g)

Overall current consumption is 260 µA.

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

Any orientation.

## 3 - Finite State Machine output values

- FSM_OUTS1 register values
  - 01h = Shock event has started
  - 00h = Shock event has ended

## 4 - Interrupts

The configuration generates two interrupts, one reporting that the shock event has started and one reporting that the shock event has ended. When the first interrupt is generated, the FSM_OUTS1 register is written to 01h. When the second interrupt is generated, the FSM_OUTS1 register is written back to 00h, and the peak tracking hardware block stores the high-g accelerometer peak value in FIFO.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2025 STMicroelectronics**
