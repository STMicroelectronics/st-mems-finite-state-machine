## 1 - Introduction

This Finite State Machine (FSM) example implements *tilt detection*, used to trigger an event when the inclination between the x-axis and the horizontal plane exceeds a specified angle.

The FSM processes data coming from the accelerometer, configured at 26 Hz and 2 g.

The tilt angle is configurable, the default is -30 degrees (-0.5 g on the x-axis).

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

The device must be placed with the x-y plane parallel to gravity. At 0 degrees of tilt the y-axis is pointing up.

## 3 - Finite State Machine output values

None.

## 4 - Interrupts

The configuration generates an interrupt on INT1 when a *tilt* of the specified angle is detected.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2025 STMicroelectronics**
