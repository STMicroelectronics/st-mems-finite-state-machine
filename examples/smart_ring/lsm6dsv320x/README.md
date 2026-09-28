## 1 - Introduction

This Finite State Machine (FSM) example implements a collection of algorithms typically used in a modern *smart ring* to activate or deactivate functionalities.

The Machine Learning Core (MLC) is used to detect two states:
- `Ready` state: when the palm of the hand is perpendicular to the ground (as when you move your hand forward to shake hands).
- `Not-ready` state: any other orientation of the hand.

The output of the MLC is used as input to the FSM. The gestures are identified only when the MLC detects the `Ready` state.

The FSM/MLC process data coming from both accelerometer and gyroscope, configured in low-power mode at 120 Hz.

Each FSM implements a specific detection:
- FSM1 implements the **flip-up** detection.
- FSM2 implements the **flip-down** detection.
- FSM3 implements the **swipe-left** detection.
- FSM4 implements the **swipe-right** detection.

The overall current consumption is 420 µA.

For information on how to integrate this algorithm in the target platform, please follow the instructions available in the README file of the [examples](../../../examples) folder.

For information on how to create similar algorithms, please follow the instructions provided in the [tutorials](../../../tutorials) folder.

## 2 - Device orientation

ENU orientation is required.

![SensorOrientation](./images/orientation.png)

## 3 - Finite State Machine output values

None.

## 4 - Interrupts

The configuration generates an interrupt on INT1 when the device is detected entering or exiting any region. The FSM generating the interrupt can be identified by reading the FSM_STATUS_MAINPAGE / FSM_STATUS register.

------

**More Information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2026 STMicroelectronics**
