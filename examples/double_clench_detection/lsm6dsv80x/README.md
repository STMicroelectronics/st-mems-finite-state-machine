## 1 - Introduction

This Finite State Machine (FSM) example implements the *double_clench* gesture. It uses the accelerometer sensor only. A *double_clench* is performed by clenching (i.e., squeezing of palm to make a fist and release) twice consecutively while looking at the smartwatch.

The configuration runs at 120 Hz.

The configuration supports both left and right wrist worn cases.

Configurable parameters:

- Clench intensity, default is 1.2 g
- Minimum time for the second clench, default is 0.25 s (30 samples)
- Maximum time before the second clench, default is 1 s (120 samples)

Overall current consumption is 231 µA.

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

ENU orientation is required

## 3 - Finite State Machine output values

None.

## 4 - Interrupts

The configuration generates an interrupt on INT1 when *double_clench* gesture is detected.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2026 STMicroelectronics**