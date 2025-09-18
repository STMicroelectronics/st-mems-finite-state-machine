# Examples

This folder contains ready-to-use examples for MEMS devices embedding the finite state machine (FSM) core.

Each folder is dedicated to a specific example and contains a `README.md` file with general information about that example and a set of sub-folders with the configuration for each of the supported MEMS sensors. Each sensor sub-folder contains:
- A `README.md` file, with information about the specific configuration.
- A `.json` file, containing the device configuration generated with STMicroelectronics tools. This file can be used to load the FSM program and sensor configuration into the sensor. For this purpose, different hardware tools provided by ST can be used ([STEVAL-MKI109D](https://www.st.com/en/evaluation-tools/steval-mki109d.html), [STM32 Nucleo](https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-mpu-eval-tools/stm32-mcu-mpu-eval-tools/stm32-nucleo-boards.html), [SensorTile.box PRO](https://www.st.com/en/evaluation-tools/steval-mkboxpro.html), etc.).
- A `.h` file, containing the same information as the `.json` file, but in the format of a C header file. Examples of `.h` file integration in C projects are available in the [platform independent drivers repository](http://www.st.com/content/st_com/en/products/embedded-software/mems-and-sensors-software/drivers-for-mems/c-driver-mems.html) for STMicroelectronics MEMS sensors.

## How to use the JSON configuration files to run the examples

### Run the example with Professional MEMS tool board and MEMS Studio

To test an FSM example in [MEMS Studio](https://www.st.com/en/development-tools/mems-studio.html) with the Professional MEMS tool board, the `.json` file has to be loaded as described in the following steps:

1. Download the latest version of MEMS Studio (if not already installed).
2. Plug the DIL24 adapter of the specific sensor to the Professional MEMS tool board.
3. Plug the Professional MEMS tool board to the PC with a USB cable.
    - If necessary, upgrade the firmware of your board using the `Firmware Programming` functionality embedded in MEMS Studio.
4. Open MEMS Studio and select the desired device (choose the COM port and the used sensor).
5. Go to `Sensor Evaluation`, `Load/Save Configuration` and load the `.json` configuration file.
6. Once the device has been configured, press the `▶` button in the top left corner to start streaming data from the sensor and visualize the FSM results in the `Data Monitor` view. You can also visualize FSM results and interrupts in a dedicated view by navigating to the `Advanced Features` menu, choosing the `FSM` option, and clicking on the `Testing` button at the bottom of the window.

### Run the example with STM32 Nucleo board and MEMS Studio

MEMS Studio can work with Nucleo boards coupled with X-NUCLEO expansion boards (for example, X-NUCLEO-IKS4A1). Optionally, the DIL24 adapter of a sensor can be plugged on top of the X-NUCLEO expansion board. Do not plug a DIL24 adapter if it hosts a sensor with the same I2C address of one of the sensors host by the X-NUCLEO board, as a clash of addresses may cause problems.

To run an FSM example in MEMS Studio with the Nucleo board, the `.json` file has to be loaded as described in the following steps:

1. Download the latest version of MEMS Studio (if not already installed).
2. Download the latest version of [X-CUBE-MEMS1](https://www.st.com/en/embedded-software/x-cube-mems1.html).
3. Plug the X-NUCLEO expansion board on top of the Nucleo board.
4. Optionally plug the DIL24 adapter hosting a sensor with FSM core in the DIL24 socket of the expansion board.
5. Plug the Nucleo board to the PC with a USB cable.
6. The Nucleo board has to be programmed with the DataLogExtended firmware from the X-CUBE-MEMS1 package (if not already programmed).
    - Locate the *DatalogExtended.bin* file in the X-CUBE-MEMS1 package under *Projects*, *STM32xxxxxx-Nucleo*, *Examples*, *IKSxxxx*, *DataLogExtended*, *Binary*.
    - Copy the *DatalogExtended.bin* file to the disk drive associated with the Nucleo board to flash the firmware.
7. Open MEMS Studio, connect to the Nucleo board, and select the desired sensors.
8. Go to `Sensor Evaluation`, `Load/Save Configuration` and load the `.json` configuration file.
9. Once the device has been configured, press the `▶` button in the top left corner to start streaming data from the sensor and visualize the FSM results in the `Data Monitor` view. You can also visualize FSM results and interrupts in a dedicated view by navigating to the `Advanced Features` menu, choosing the `FSM` option, and clicking on the `Testing` button at the bottom of the window.

### Run the example with SensorTile.box PRO / STWIN.box and MEMS Studio

To test an FSM example in MEMS Studio with the SensorTile.box PRO / STWIN.box board, the `.json` file has to be loaded as described in the following steps:

1. Download the latest version of MEMS Studio (if not already installed).
2. If necessary, plug the DIL24 adapter of the specific sensor to the Professional MEMS tool board.
3. Plug the SensorTile.box PRO / STWIN.box board to the PC with a USB cable.
    - If necessary, upgrade the firmware of your board using the `Firmware Programming` functionality embedded in MEMS Studio.
4. Open MEMS Studio and select the desired device (choose the COM port and the used sensor).
5. Go to `Sensor Evaluation`, `Load/Save Configuration` and load the `.json` configuration file.
6. Once the device has been configured, press the `▶` button in the top left corner to start streaming data from the sensor and visualize the FSM results in the `Data Monitor` view. You can also visualize FSM results and interrupts in a dedicated view by navigating to the `Advanced Features` menu, choosing the `FSM` option, and clicking on the `Testing` button at the bottom of the window.

## Examples per device

* ASM330LHB
	* [motion_stationary_detection](./motion_stationary_detection/asm330lhb)
	* [shake_detection](./shake_detection/asm330lhb)
* ASM330LHBG1
	* [motion_stationary_detection](./motion_stationary_detection/asm330lhbg1)
	* [shake_detection](./shake_detection/asm330lhbg1)
* ASM330LHHX
	* [motion_stationary_detection](./motion_stationary_detection/asm330lhhx)
	* [shake_detection](./shake_detection/asm330lhhx)
* ASM330LHHXG1
	* [motion_stationary_detection](./motion_stationary_detection/asm330lhhxg1)
	* [shake_detection](./shake_detection/asm330lhhxg1)
* IIS2DULPX
	* [fourd_orientation_detection](./fourd_orientation_detection/iis2dulpx)
	* [free_fall_detection](./free_fall_detection/iis2dulpx)
	* [motion_stationary_detection](./motion_stationary_detection/iis2dulpx)
* IIS2ICLX
	* [tilt_detection](./tilt_detection/iis2iclx)
* ISM330BX
	* [fourd_orientation_detection](./fourd_orientation_detection/ism330bx)
	* [free_fall_detection](./free_fall_detection/ism330bx)
	* [motion_stationary_detection](./motion_stationary_detection/ism330bx)
* ISM330DHCX
	* [fourd_orientation_detection](./fourd_orientation_detection/ism330dhcx)
	* [free_fall_detection](./free_fall_detection/ism330dhcx)
	* [motion_stationary_detection](./motion_stationary_detection/ism330dhcx)
* ISM6HG256X
	* [fourd_orientation_detection](./fourd_orientation_detection/ism6hg256x)
	* [free_fall_detection](./free_fall_detection/ism6hg256x)
	* [lift_detection](./lift_detection/ism6hg256x)
	* [motion_stationary_detection](./motion_stationary_detection/ism6hg256x)
	* [peak_tracking](./peak_tracking/ism6hg256x)
	* [pick_up_detection](./pick_up_detection/ism6hg256x)
	* [shake_detection](./shake_detection/ism6hg256x)
* LIS2DUX12
	* [flip_down_detection](./flip_down_detection/lis2dux12)
	* [flip_up_detection](./flip_up_detection/lis2dux12)
	* [fourd_orientation_detection](./fourd_orientation_detection/lis2dux12)
	* [free_fall_detection](./free_fall_detection/lis2dux12)
	* [glance_detection](./glance_detection/lis2dux12)
	* [jiggle_detection](./jiggle_detection/lis2dux12)
	* [lift_detection](./lift_detection/lis2dux12)
	* [motion_stationary_detection](./motion_stationary_detection/lis2dux12)
	* [pick_up_detection](./pick_up_detection/lis2dux12)
	* [shake_detection](./shake_detection/lis2dux12)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lis2dux12)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lis2dux12)
* LIS2DUXS12
	* [flip_down_detection](./flip_down_detection/lis2duxs12)
	* [flip_up_detection](./flip_up_detection/lis2duxs12)
	* [fourd_orientation_detection](./fourd_orientation_detection/lis2duxs12)
	* [free_fall_detection](./free_fall_detection/lis2duxs12)
	* [glance_detection](./glance_detection/lis2duxs12)
	* [jiggle_detection](./jiggle_detection/lis2duxs12)
	* [lift_detection](./lift_detection/lis2duxs12)
	* [motion_stationary_detection](./motion_stationary_detection/lis2duxs12)
	* [pick_up_detection](./pick_up_detection/lis2duxs12)
	* [shake_detection](./shake_detection/lis2duxs12)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lis2duxs12)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lis2duxs12)
* LSM6DSO
	* [flip_down_detection](./flip_down_detection/lsm6dso)
	* [flip_up_detection](./flip_up_detection/lsm6dso)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dso)
	* [free_fall_detection](./free_fall_detection/lsm6dso)
	* [lift_detection](./lift_detection/lsm6dso)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dso)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dso)
	* [pick_up_detection](./pick_up_detection/lsm6dso)
	* [shake_detection](./shake_detection/lsm6dso)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dso)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dso)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dso)
* LSM6DSO32
	* [flip_down_detection](./flip_down_detection/lsm6dso32)
	* [flip_up_detection](./flip_up_detection/lsm6dso32)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dso32)
	* [free_fall_detection](./free_fall_detection/lsm6dso32)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dso32)
	* [shake_detection](./shake_detection/lsm6dso32)
* LSM6DSO32X
	* [flip_down_detection](./flip_down_detection/lsm6dso32x)
	* [flip_up_detection](./flip_up_detection/lsm6dso32x)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dso32x)
	* [free_fall_detection](./free_fall_detection/lsm6dso32x)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dso32x)
	* [shake_detection](./shake_detection/lsm6dso32x)
* LSM6DSOX
	* [flip_down_detection](./flip_down_detection/lsm6dsox)
	* [flip_up_detection](./flip_up_detection/lsm6dsox)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsox)
	* [free_fall_detection](./free_fall_detection/lsm6dsox)
	* [glance_detection](./glance_detection/lsm6dsox)
	* [jiggle_detection](./jiggle_detection/lsm6dsox)
	* [lift_detection](./lift_detection/lsm6dsox)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsox)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsox)
	* [pick_up_detection](./pick_up_detection/lsm6dsox)
	* [shake_detection](./shake_detection/lsm6dsox)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsox)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsox)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsox)
* LSM6DSR
	* [flip_down_detection](./flip_down_detection/lsm6dsr)
	* [flip_up_detection](./flip_up_detection/lsm6dsr)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsr)
	* [free_fall_detection](./free_fall_detection/lsm6dsr)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsr)
	* [shake_detection](./shake_detection/lsm6dsr)
* LSM6DSRX
	* [flip_down_detection](./flip_down_detection/lsm6dsrx)
	* [flip_up_detection](./flip_up_detection/lsm6dsrx)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsrx)
	* [free_fall_detection](./free_fall_detection/lsm6dsrx)
	* [glance_detection](./glance_detection/lsm6dsrx)
	* [jiggle_detection](./jiggle_detection/lsm6dsrx)
	* [lift_detection](./lift_detection/lsm6dsrx)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsrx)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsrx)
	* [pick_up_detection](./pick_up_detection/lsm6dsrx)
	* [shake_detection](./shake_detection/lsm6dsrx)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsrx)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsrx)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsrx)
* LSM6DSV
	* [flip_down_detection](./flip_down_detection/lsm6dsv)
	* [flip_up_detection](./flip_up_detection/lsm6dsv)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsv)
	* [free_fall_detection](./free_fall_detection/lsm6dsv)
	* [lift_detection](./lift_detection/lsm6dsv)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsv)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsv)
	* [pick_up_detection](./pick_up_detection/lsm6dsv)
	* [shake_detection](./shake_detection/lsm6dsv)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsv)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsv)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsv)
* LSM6DSV16B
	* [flip_down_detection](./flip_down_detection/lsm6dsv16b)
	* [flip_up_detection](./flip_up_detection/lsm6dsv16b)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsv16b)
	* [free_fall_detection](./free_fall_detection/lsm6dsv16b)
	* [lift_detection](./lift_detection/lsm6dsv16b)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsv16b)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsv16b)
	* [pick_up_detection](./pick_up_detection/lsm6dsv16b)
	* [shake_detection](./shake_detection/lsm6dsv16b)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsv16b)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsv16b)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsv16b)
* LSM6DSV16BX
	* [flip_down_detection](./flip_down_detection/lsm6dsv16bx)
	* [flip_up_detection](./flip_up_detection/lsm6dsv16bx)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsv16bx)
	* [free_fall_detection](./free_fall_detection/lsm6dsv16bx)
	* [glance_detection](./glance_detection/lsm6dsv16bx)
	* [jiggle_detection](./jiggle_detection/lsm6dsv16bx)
	* [lift_detection](./lift_detection/lsm6dsv16bx)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsv16bx)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsv16bx)
	* [pick_up_detection](./pick_up_detection/lsm6dsv16bx)
	* [shake_detection](./shake_detection/lsm6dsv16bx)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsv16bx)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsv16bx)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsv16bx)
* LSM6DSV16X
	* [flip_down_detection](./flip_down_detection/lsm6dsv16x)
	* [flip_up_detection](./flip_up_detection/lsm6dsv16x)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsv16x)
	* [free_fall_detection](./free_fall_detection/lsm6dsv16x)
	* [glance_detection](./glance_detection/lsm6dsv16x)
	* [jiggle_detection](./jiggle_detection/lsm6dsv16x)
	* [lift_detection](./lift_detection/lsm6dsv16x)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsv16x)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsv16x)
	* [pick_up_detection](./pick_up_detection/lsm6dsv16x)
	* [shake_detection](./shake_detection/lsm6dsv16x)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsv16x)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsv16x)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsv16x)
* LSM6DSV320X
	* [flip_down_detection](./flip_down_detection/lsm6dsv320x)
	* [flip_up_detection](./flip_up_detection/lsm6dsv320x)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsv320x)
	* [free_fall_detection](./free_fall_detection/lsm6dsv320x)
	* [glance_detection](./glance_detection/lsm6dsv320x)
	* [jiggle_detection](./jiggle_detection/lsm6dsv320x)
	* [lift_detection](./lift_detection/lsm6dsv320x)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsv320x)
	* [peak_tracking](./peak_tracking/lsm6dsv320x)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsv320x)
	* [pick_up_detection](./pick_up_detection/lsm6dsv320x)
	* [shake_detection](./shake_detection/lsm6dsv320x)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsv320x)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsv320x)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsv320x)
* LSM6DSV32X
	* [flip_down_detection](./flip_down_detection/lsm6dsv32x)
	* [flip_up_detection](./flip_up_detection/lsm6dsv32x)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsv32x)
	* [free_fall_detection](./free_fall_detection/lsm6dsv32x)
	* [glance_detection](./glance_detection/lsm6dsv32x)
	* [jiggle_detection](./jiggle_detection/lsm6dsv32x)
	* [lift_detection](./lift_detection/lsm6dsv32x)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsv32x)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsv32x)
	* [pick_up_detection](./pick_up_detection/lsm6dsv32x)
	* [shake_detection](./shake_detection/lsm6dsv32x)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsv32x)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsv32x)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsv32x)
* LSM6DSV80X
	* [flip_down_detection](./flip_down_detection/lsm6dsv80x)
	* [flip_up_detection](./flip_up_detection/lsm6dsv80x)
	* [fourd_orientation_detection](./fourd_orientation_detection/lsm6dsv80x)
	* [free_fall_detection](./free_fall_detection/lsm6dsv80x)
	* [glance_detection](./glance_detection/lsm6dsv80x)
	* [jiggle_detection](./jiggle_detection/lsm6dsv80x)
	* [lift_detection](./lift_detection/lsm6dsv80x)
	* [motion_stationary_detection](./motion_stationary_detection/lsm6dsv80x)
	* [peak_tracking](./peak_tracking/lsm6dsv80x)
	* [phone_to_ear_detection](./phone_to_ear_detection/lsm6dsv80x)
	* [pick_up_detection](./pick_up_detection/lsm6dsv80x)
	* [shake_detection](./shake_detection/lsm6dsv80x)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/lsm6dsv80x)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/lsm6dsv80x)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/lsm6dsv80x)
* ST1VAFE3BX
	* [flip_down_detection](./flip_down_detection/st1vafe3bx)
	* [flip_up_detection](./flip_up_detection/st1vafe3bx)
	* [fourd_orientation_detection](./fourd_orientation_detection/st1vafe3bx)
	* [free_fall_detection](./free_fall_detection/st1vafe3bx)
	* [glance_detection](./glance_detection/st1vafe3bx)
	* [jiggle_detection](./jiggle_detection/st1vafe3bx)
	* [lift_detection](./lift_detection/st1vafe3bx)
	* [motion_stationary_detection](./motion_stationary_detection/st1vafe3bx)
	* [pick_up_detection](./pick_up_detection/st1vafe3bx)
	* [shake_detection](./shake_detection/st1vafe3bx)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/st1vafe3bx)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/st1vafe3bx)
* ST1VAFE6AX
	* [flip_down_detection](./flip_down_detection/st1vafe6ax)
	* [flip_up_detection](./flip_up_detection/st1vafe6ax)
	* [fourd_orientation_detection](./fourd_orientation_detection/st1vafe6ax)
	* [free_fall_detection](./free_fall_detection/st1vafe6ax)
	* [glance_detection](./glance_detection/st1vafe6ax)
	* [jiggle_detection](./jiggle_detection/st1vafe6ax)
	* [lift_detection](./lift_detection/st1vafe6ax)
	* [motion_stationary_detection](./motion_stationary_detection/st1vafe6ax)
	* [phone_to_ear_detection](./phone_to_ear_detection/st1vafe6ax)
	* [pick_up_detection](./pick_up_detection/st1vafe6ax)
	* [shake_detection](./shake_detection/st1vafe6ax)
	* [wrist_navigation_gestures_recognition](./wrist_navigation_gestures_recognition/st1vafe6ax)
	* [wrist_tilt_detection_accelerometer_gyroscope](./wrist_tilt_detection_accelerometer_gyroscope/st1vafe6ax)
	* [wrist_tilt_detection_accelerometer_only](./wrist_tilt_detection_accelerometer_only/st1vafe6ax)

------

**More information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2025 STMicroelectronics**
