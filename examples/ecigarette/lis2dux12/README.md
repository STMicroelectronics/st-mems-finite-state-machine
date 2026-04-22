## 1 - Introduction

This Finite State Machine (FSM) example implements a collection of algorithms typically used in a modern *e-cigarette* to activate or deactivate functionalities and adapt the e-cigarette user interface based on its orientation.

The Machine Learning Core (MLC) is used to:
- Low-pass filter acceleration on each axis with 1 Hz cutoff frequency.
- High-pass filter acceleration norm with 1 Hz cutoff frequency.
- Detect four regions through four decision trees:
  - Tilt-low region.
  - Tilt-high region.
  - Horizontal-left region.
  - Horizontal-right region.

The output of the MLC is used as input to the FSM.

The FSM/MLC process data coming from the accelerometer, configured in low-power mode at 25 Hz.

Each FSM implements a specific detection:
- FSM #1 implements the **tilt-low** detection by using the first decision tree output as input.
- FSM #2 implements the **tilt-high** detection by using the second decision tree output as input.
- FSM #3 implements the **horizontal-left** detection by using the third decision tree output as input.
- FSM #4 implements the **horizontal-right** detection by using the fourth decision tree output as input.
- FSM #5 implements the **table** detection by using the MLC filtered data as input.
- FSM #6 implements the **cone** detection by using the MLC filtered data as input.
- FSM #7 implements the **portrait-up** detection by using the MLC filtered data as input.
- FSM #8 implements the **portrait-down** detection by using the MLC filtered data as input.

The overall current consumption is 20.8 µA.

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

ENU orientation is required.

## 3 - Finite State Machine output values

- FSM_OUTS1 register values
  - 00h = Tilt-low region out event
  - 01h = Tilt-low region in event
- FSM_OUTS2 register values
  - 00h = Tilt-high region out event
  - 01h = Tilt-high region in event
- FSM_OUTS3 register values
  - 00h = horizontal-left region out event
  - 01h = horizontal-left region in event
- FSM_OUTS4 register values
  - 00h = horizontal-right region out event
  - 01h = horizontal-right region in event
- FSM_OUTS5 register values
  - 00h = table region out event
  - 01h = table region in event
- FSM_OUTS6 register values
  - 00h = cone region out event
  - 01h = cone region in event
- FSM_OUTS7 register values
  - 00h = portrait-up region out event
  - 01h = portrait-up region in event
- FSM_OUTS8 register values
  - 00h = portrait-down region out event
  - 01h = portrait-down region in event

## 4 - Interrupts

The configuration generates an interrupt on INT1 when the device is detected entering or exiting any region. The FSM generating the interrupt can be identified by reading the FSM_STATUS_MAINPAGE / FSM_STATUS register and the FSM event can be identified by reading the corresponding FSM_OUTSx register.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2026 STMicroelectronics**

