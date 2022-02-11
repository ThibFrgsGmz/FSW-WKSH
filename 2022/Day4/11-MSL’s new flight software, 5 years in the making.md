| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |

---

Q: Does you FSW have a backup copy onboard? do you apply the hot/cold patch to the backup copy also?

A: Yes! For our main computer, we have two main images and two more backups.  We install a hot patch on just the main image at runtime.  We install a cold patch on the two main images.  And the two backups just hang out, waiting for work.

---

Q: In what circumstances would you use a cold patch versus a full update?

A: We had to apply a very small but very important patch to address an issue we’ve only seen once.  To guarantee we never see the issue again, and ASAP, we applied the patch and burned it into the non-volatile memory.  A full update would take months to complete.  Our super-duper-fast one, called R-Hope, took 18 months!
I see the benefit of just recompiling, testing the parts that changed, and flying that.
However… our flight software is big. It takes a month or more just to upload the pieces via the DSN, and lots of careful coordination with our orbiter partners to get our files relayed to the spacecraft.
A patch can be uplinked in a day or two.

---

Q: Are cold patches called "cold" because they are applied at night?

A: It’s a “cold” patch because it’s going to be applied even from a “cold” boot.  In contrast, a “hot” patch needs to be applied “hot,” or while the computer is on & running.


