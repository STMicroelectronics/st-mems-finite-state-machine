# FSM - finite state machine

This repository provides examples and tutorials of the **finite state machine (FSM)**, a dedicated core available in some products of the [**ST MEMS sensors portfolio**](http://st.com/MEMS).

The FSM core processing capability allows moving some algorithms from the application processor to the MEMS sensor, enabling consistent reduction of power consumption.

The FSM core can be configured to detect user-defined motion patterns through finite state machines. A finite state machine is a mathematical abstraction used to design logical connections. It is a behavioral model composed of a finite number of states and transitions between states, similar to a flowchart in which it is possible to inspect how the logic runs when certain conditions are met. The finite state machine begins with a *Start* state, moves to different states through transitions dependent on the inputs, and finally ends in a *Stop* state. The current state is uniquely determined by the past states of the system.

The results of the FSM core can be read from the application processor at any time. Furthermore, there is the possibility to **generate an interrupt** when a user-defined motion pattern is detected.

## Repository overview

This repository is structured as follows:

- An [examples](./examples/) folder, containing examples of applications ready to be used with the sensors.
- A [tutorials](./tutorials/) folder, containing tutorials describing how to create solutions using different ST hardware kits and software tools.

------

**More information: [http://www.st.com](http://st.com/MEMS)**

**Copyright © 2025 STMicroelectronics**
