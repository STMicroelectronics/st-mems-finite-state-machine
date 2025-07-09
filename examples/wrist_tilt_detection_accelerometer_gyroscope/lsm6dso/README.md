## 1 - Introduction

This Finite State Machine (FSM) example implements the *wrist-tilt* gesture typically used in wrist worn devices to signal the intention of the user to look at the device screen. It is typically used to automatically turn on the device screen.

The FSM processes data coming from both accelerometer and gyroscope, configured in low-power mode at 52 Hz.

The two configurations for left wrist worn case and right worn case are provided separately.

Configurable parameters:

- Angular rate to start / stop gyroscope integration, default is 0.175 rad/s
- Wrist-tilt rotation angle, default is 40 degrees (0.698 rad)
- Accelerometer threshold on +x (for left wrist) or -x (for right wrist) and +y axis, default is -0.5 g
- +y check time, default is 154 ms (8 samples)

Overall current consumption is 300 µA.

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

ENU orientation is required.

## 3 - Finite State Machine output values

None.

## 4 - Interrupts

The configuration generates an interrupt on INT1 when the *wrist-tilt* gesture is detected.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2025 STMicroelectronics**

