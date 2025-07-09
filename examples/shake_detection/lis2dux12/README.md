## 1 - Introduction

Simple *shake* gesture example for smartphone devices. This gesture is detected when the user is shaking the accelerometer along the X-axis.

The FSM processes data coming from the accelerometer, configured in ultra low-power mode at 25 Hz.

Overall current consumption is 10.7 µA.

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

ENU orientation is required.

## 3 - Finite State Machine output values

None.

## 4 - Interrupts

The configuration generates an interrupt on INT1 when the *shake* gesture is detected.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2025 STMicroelectronics**