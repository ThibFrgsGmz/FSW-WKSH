| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |


---

Q : With the kernel/RTP bifurcation, how does your system deal with interrupt?

A: We are planning on handling interrupts down in the PSP.
The ISR services the interrupt and then moves data to the correct memory space
