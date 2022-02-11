| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |

Collaboration between Blue Origin (prime contractor), NASA and Open Robotics.

Development rationale: there is no space-quality software framework for intelligent, autonomous, collaborative robotic systems.

This is a software framework for maturing space-qualified robotic software based on an open community, frameworks and standards.

It aims to be modular/reusable/adoptable/quality controller/real time and deterministic/strict memory management.

The space community wants an open source framework that does for space robotics what the cFS developed by NASA for FSW spacecraft and F Prime does for SmallSat/Equipment.

SpaceROS will be aligned with space industry software quality standards. It will comply with critical software safety standards such as DO-178C and NASA NPR 7150.2c.

SpaceROS will also align with standards such as CCSDS, ISO/IEC (ISO 26262) and FACE. FACE is a new Open Group standard aimed at standardizing avionics in the military aerospace community.

SpaceROS is developing a new continuous integration system that collects software conformance artifacts from the requirements stage through the construction of the unit test software. The goal is to provide a system that supports software quality and compliance activities. They provide a system that automates the software qualification process.

Tools used in the CI:
- FRET (Formal Requirements Elicitation Tool): automated requirements verification.
- Flawfinder: identifies cybersecurity issues related to the Common Weakness Enumeration (CWE).
- IKOS: C++ static analysis
- Cppcheck: C static analysis
- clang: Clang static analyzer suites
- Cobra: Coding compliance checks such as Coding Styles, MISRA, POWER OF 10
- gcov : coverage
- Valgrind: memory usage
- SCRUB: static layout analysis output.

They will respect the CCSDS Space Packet protocol and the CCSDS Asynchronous Message service (implementation available in open source).

To avoid the need for a hardware platform, they will exploit the concept of digital twins (https://www.cadlog.fr/key-topics/digital-twin/). Many Open Source technologies allow the emulation of these platforms such as :

- Renodes https://github.com/renode/renode
- QEMU https://github.com/qemu/qemu

---

Q: Do you plan to release only the source code or also a pre-qualification package similar to RTEMS pre-qualification?
A: We are in the process of emulating this model.

---

Q: I have also tried the Renode.io simulator. I can run the cFS on RTEMS on the LEON3 model. I have been working until the network interface works for this target. I believe network interfaces are only supported on Linux hosts at this time.
A: Renode has a LEON3FT target, I ran RTEMS on it yesterday.

---

Comments on Renode between Joel Sherill (RTEMS OAR) and Alan Curdmore (NASA GSFC):
JS: Gedare and I discussed potential GSoC projects. They may be small or large this year. I wondered if there was anything to do with renode.io. Your comment made me think you might be able to use a student.

AC: Renode is interesting, but I don't know if I'm sold on it versus continuing to use QEMU. For GSOC, I think there is still work to be done on Raspberry Pi BSPs, including support for the Raspberry Pi 4, support for the Raspberry Pi Zero W 2 (it's a brand new Pi Zero with the Pi 3 Quad A53 CPU for $15 USD), and LibBSD support. The Pi 4 might be a good candidate for a 64-bit ARM port.

JS; I agree that yet another leon simulator is not very interesting (sis, qemu, tsim, etc). But I had hoped that it might have value on some of the other SoCs for which we don't have a simulator. At least it would allow us to start building a model if they have other simulation targets that we might be interested in.

AC: That's right! You can take a look at the targets here: https://github.com/renode/renode/tree/master/platforms
One potential benefit of Renode is that it allows for simulation of multiple node models:
https://github.com/renode/renode/tree/master/scripts/multi-node 

