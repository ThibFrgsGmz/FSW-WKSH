| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| 1:45 PM | 2:10 PM	 | DEMO - APL Autonomy Engine Overview | T. Adrian Hill | JHU/APL |

Autonomy System is a Monitor->Response system

------

Q: Available via open source/NASA release?

A: Unfortunately it is not

------

Q: How much CPU load does a full set of autonomy rules consume (i.e. 100 rules consumes 1% of CPU)?

A: Great question.  On an 80 MHZ LEON it was 125 autonomy rules (or computed telemetry) for 1% of CPU. 

------

Q: How does the onboard engine translate from a symbolic representation (i.e. BUS_CURRENT) to an actual measurement (i.e. a specific channel or "pin") sample?

A: To minimize flight computation complexity, our ground tools translated the telemetry symbols to physical location (telemetry APID and byte offset in our case).
So the on-board engine just operated on packed ID and byte offset (no symbolic lookup).

------

Q: Since the autonomy engine seems like a pretty powerful compute engine, have you considered expanding its use beyond fault handing to more general control of the vehicle?

A: Yes, I think we have a lot of untapped potential there.
It has so far been used 95% for faults, 5% for operations.
One challenge has been educated our mission ops teams and planners on how to use it and program in it.
But I think there is huge potential.

------

Q: What is the difference of computational load of using 1 Autonomy rule compared to using 150 rules? Have you experience any sensible difference?

A: See not above about CPU Loading

------

Q: If after reboot the Autonomy Engine will be using default values for Autonomy Objects, the defaults may not be valid for the last state in which the system was ?

A: Yes it does default back to the initial condition.
It surprisingly has not been as much of an issue.
I would say that our rules are designed knowing that upfront.
If we need to persist something across reboot cycles we would need so external way to preserve that data (e.g., relays).


------

Q: Are there rules or limitations for commands that can be issued in macros? i.e. argument numbers or types...

A: None.  If you can send it from the ground then it can be in a macro.

------

Q: Also implementers of those commands have to follow a certain template?

A: There is a "template" and it looks pretty much the same for all four type (rules, macros, computed telemetry and storage variables).
So it ends up being pretty natural for the autonomy developers (same look and feel for all object types).


------

Q: How fast have you exercise one of your autonomy rules?

A: Not sure if I am answering the right question.
The Autonomy Engine in FSW runs at 1 Hz (although it could be run at a faster rate in FSW; we have never elected to do so).
So a rule could respond in one second. 

------

Q: What design suggestions would you make to this tool for Human-Rated/Class-A Missions?

A: I am probably out of my element there.  My experience has all been in robotic flight

------
Q: What are the advantages of your Autonomy System in comparison with more classic approaches like dynamic linking, as, for example, provided in RTEMS?

A: Fair question.  I would say that the Autonomy System is OS-independent and processor-independent and would work on a platform that does not support dynamic linking.  With dynamic linking you are still modifying FSW which may be an issue depending on the mission's risk posture.

