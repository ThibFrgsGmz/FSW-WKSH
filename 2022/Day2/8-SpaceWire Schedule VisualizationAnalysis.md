| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |


FSW Attitude Control System (ACS)

Matlab/Simulink algorithms are wrapped in C code.
Data is sent from/to the ground system and is received by the Simulink model.
Communicates with the ACS components via the SpaceWire bus.

To encode their SpaceWire program, they create a flat file format (in YAML).
They created a Python module to convert these files into graphics.
All this allowed them to create an IMAP FSW version of the SpaceWire schedule that allows for quick updates of the SpaceWire schedule.



The tool is not yet open source, but it will be soon, most probably under the MIT license.