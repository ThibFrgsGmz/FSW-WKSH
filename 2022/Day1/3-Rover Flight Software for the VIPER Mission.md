| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| 12:40 PM  | 1:05 PM  | Rover Flight Software for the VIPER Mission  | Hans Utz | NASA Ames |


The objective of the mission is to send a Rover to the south pole of the Moon (Nobile region). This is to characterize the surface and supersurface water ice and around the permanently shaded regions.

The architecture is divided into two quanta:

Embedded - Rover Flight Software (RFSW)
- FSW HW
- Operational Safety
- Basic mobility of the Rover on the surface
- Component-oriented architecture based on cFS/cFE
- Implemented in C++ (overlay layer called CoreApplet)
- Two PPCs with VxWorks
    - main radiation processor (RAD750, 1GB RAM)
    - radiation co-processor (SP0-S, 1GHz, 1GB RAM).

Off-board - Rover Ground Software (RGSW)
- Deployed on the ground
- Mobile robotics functions
- Based on the ROS2 open source framework
- Runs on Linux x86 workstations

As interface definition language (IDL), they do not use EDS but XTCE. The XTCE that is used on their Open Source Yamcs land system.

These XTCEs are used to define the interfaces between the ground and the flight, the hardware interfaces to the flight software. They act as a single source of truth between different targets (PPC, x86 Linux).

They test their flight software on x86 Linux computers and have complementary software such as Vlagrind, Cachgrind, etc.


They also use a PPC software emulation with QEMU RAD750 VxWorks running on each development computer.

They are running DevOps with 7 releases (requirements, unit testing and acceptance with the customer each time).

Two week sprints with a ShowAndTell each time.

In their continuous integration environment, they
    Build all software from source on both supported platforms (PPC and x86 Linux)
    Run all automated tests, unit tests, subsystems and end-to-end tests.

End-to-end testing is performed through their RSIM which fully simulates the entire rover to machine hosts (sensor inputs, cameras, etc.).
Their test scripts are written in Python.
