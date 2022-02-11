| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |

---

Q: Will this work on a Raspberry Pi?
A: The basic system will work on a Raspberry Pi - but there is no working network interface on RTEMS for the Pi yet! Hopefully that can be fixed in a future Google Summer of Code project.
I would have liked to show a demo like this on my "ProtoSat" - But this board relies on Linux for now!
https://github.com/alanc98/ProtoSat

---

Q: Where is rtems tree located?

A: The RTEMS tree is in the docker image - if you look through the docker directory you can see where the RTEMS repos are cloned and the tools, BSP, and LibBSD are compiled.

---

Q: Is there a similar Docker setup for VxWorks?

A: I have seen a Docker setup for vxWorks, but obviously it would not be distributable - In my case, the docker image only provides the tools to build. If you could add your VxWorks SDK to an image it would be the equivalent setup.

---

Q: Is it possible to statically link everything (including tables and startup script) so that no filesystem is needed at all?

A: You can link the OS Image, cFE Core, and all of the apps together, but you currently need a file system for the tables and startup script.
cFE core also creates a RAM disk for logs and temporary files.

