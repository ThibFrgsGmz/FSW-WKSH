| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |

# Challenges

It is extremely challenging to design a software architecture that meets the needs of multiple spacecraft domains while allowing for domain-level software reuse.

FSW is closely related to the protocols of satellite-ground, intra-satellite and inter-satellite. It is difficult to design software that organically adapts and integrates with ground-to-satellite, intra-satellite, and inter-satellite protocols in various domains.

The spacecraft is equipped with a diverse set of hardware and interfaces. It is extremely difficult to develop software that can accommodate different hardware and interfaces.

A flexible unified software architecture (FUHSI) jig has been designed and implemented to address this challenge.

# Design principles

- A multi-layered design.
- A unified framework for standardizing operating system and driver interfaces.
- A unified mechanism for the transmission of information.
- Standardization of components and component interfaces

# Domain Requirement Analysis

They integrate in their architecture:
- CCSDS Spacecraft Onboard Interface Services (SOIS);
- CCSDS Space Link Services (SLS);
- CCSDS Space Internetworking Services (SIS);
- ECSS Packet Utilization Standard (PUS).

# Software Architecture Design

Their architecture is reference in the CCSDS Orange Book: CCSDS 811.1-O-1.

# Avionic System Prototype 2

One can notice the integration of the time-triggered Ethernet protocol in the topology of their prototype.

# Application in SmallSat

They deployed their architecture on a SmallSat that will be launched in 2022. They had to switch from MIL-STD-1553 bus to CAN bus.
They are reusing 75% of the core components.

# Benefits of using FUHSI

- The data transmission mechanism has been made more adaptable.
- It allows to replace the interface without affecting the application software of the upper layer.
- It allows to increase the computing capacity of the system according to the needs.
- The transfer layer connects space and on-board communications.
- To ensure system functionality, the services are combined.
- Create a new model for embedded software development.

**NOTE**: they are considering releasing it as open source!