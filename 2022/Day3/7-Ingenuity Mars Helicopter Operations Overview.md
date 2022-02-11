| Start Time   | End Time  | Title  | Facilitator/Speaker  | Organization  |
|:---:|:---:|:---:|:---:|:---:|
| xxx | x | xxxxxxxxx | xx | xxx |

---

Q: Why the flight time is so little? Isn't it's weight less on Mars so you could increase the battery capacity?

A: We had to balance between battery size and mass, and the batteries we have conservatively give us the times we fly. As time has gone on, we have exceeded what we thought we could do initially.

---

Q: Are there lessions learned from the copter that might be applicable or useful to the Dragonfly mission?

A: I'm sure there are related to GNC algorithms. I know there has been contact between our team and Dragonfly.

---

Q: Have dust devils been a “blessing” or a hindrace to  the helicopter operation ?

A: We have one cool picture from the rover where you can see a dust-devil in the background during a flight, but so far there is no evidence that one interacted directly with the helicopter.

---

Q: How is radiation tolerance of current and newer Qualcomm parts?

A: Without getting into testing data which can't really be released here, the results were good enough that we were confident we could operate safely on Mars.

---

Q: Which control algorythm is used in helicopter?

A: I would defer to the GNC team for this and stay in my lane. :visage_légèrement_souriant: Here is a paper:
https://rotorcraft.arc.nasa.gov/Publications/files/Balaram_AIAA2018_0023.pdf

---

Q: Given the use of commercial and COTS components, did you need to do anything special to qualify the helicopter for temperature ranges and launch vibration?

A: We did take the helicopter and base station through  a full set of environmental testing to verify the flight article could function at the temperatures and launch/EDL loads we would see.

---

Q: Did you collect data on how many radiation related issues you got with the Snapdragon?

A: If you mean during development, we did radiation testing on the hardware. For operations, we've only seen one minor memory bit flip, but otherwise haven't seen anything attributable to radiation.

---

Q: Did you use magnetometer in IMU? Did you have any issues with magnet field of mars?
A: We didn't use the magnetometer part of the IMU, just rates/gyro.

---

Q: Are there any lessons learned from using a Linux based system? Any info on the composition of this system, such as are you using a Yocto root filesystem or something else?

A: We received the build from Qualcomm, and they use Yocto to compose it. We rebuilt it from time to time to turn features on or off. The Linux we had was the preempt version but not the RT version.
The processor is so fast, it didn't really hurt us, and we built in robustness to cycle slips assuming there could be some under non-RT Linux. Some high-level lessons could be:
1) You will have to trust code you probably can't see or don't have time to see, so testing is key;
2) Build robustness into the system for the inevitable glitches in the non-realtime kernel.
3) Having a command line is great, so provide a commanding path there.
4) You really need to have a person dedicated to understanding the system to inform you of what to expect and how to configure it.

---

Q: Could you tell us any stories about the work between JPL and Github to create the Mars 2020 Helicopter Contributor badge? https://github.blog/2021-04-19-open-source-goes-to-mars/

A: It started with this article: https://spectrum.ieee.org/nasa-designed-perseverance-helicopter-rover-fly-autonomously-mars
In the last paragraph I mention F Prime as an open source framework on GitHub. GitHub caught wind of it, and wanted to do something to promote open source, and since everybody was interested in Ingenuity at the time, they proposed the badge.
They did a scan of the software the repo references and traced all the dependencies back to developers, and gave them the badge. It was a way to show that many developers throughout open source can contribute to something cool like the helicopter, even if they didn't work on it directly.

