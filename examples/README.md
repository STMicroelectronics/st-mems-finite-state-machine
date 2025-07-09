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

------

**More information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2025 STMicroelectronics**
