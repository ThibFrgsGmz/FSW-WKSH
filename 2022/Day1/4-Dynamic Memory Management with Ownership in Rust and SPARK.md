| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| 1:05 PM | 1:30 PM | AdaCore - Dynamic Memory Management with Ownership in Rust and SPARK  | Dr. Yannick Moy | AdaCore |

Christopher Heistand raises that part of the problem with Rust adoption is that C/C++ has been used for so long that there are workarounds for everything.
And that it requires a case of real-world problems being solved to move to a language like Rust."

Yannick Moy has no anecdote to share but that people don't use dynamic memory to its full potential because of the objective cost of certifying it.
Typically, when dynamic memory is used, it's done manually at application startup, and never deallocated. This suits some use cases but not all.

The community is becoming more and more interested in Rust, whether it be universities or private companies.

Zachary Catlin of Penn State plans to use Rust next year to develop software for flying an astronomy instrument for CubeSat.
This software would be developed as a cFS application package. The Rust binding code with the cFE/cFS/OSAL API will most likely be released as open source.

As Rust grows in the larger non-FSW community, supported by GAFAM, we can expect a lot of push in the FSW community.
As more libraries are developed in Rust, we could integrate them directly into FSW.

Leonidas Kosmidis shares the results of his work on "Industrial experiences with resource management under software randomization in ARINC653 avionics environments".

One of his thesis contributions was on software randomization for (probabilistic) WCET computation, and they applied it to two avionics applications on top of an ARINC-653 RTOS.
They modified their runtime system to perform all (dynamic) allocations at startup from a fixed size memory pool.
But determining the new partition limits (mainly memory and time) for the application configuration was a real challenge.