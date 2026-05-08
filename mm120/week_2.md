# WEEK 2

    Author: Idris Ispandi
    Feb 16 2026

### Initial Conversation with the machine shop. 
After submitting our proposal we figured out the general direction for the electronics part.

Next we approached __Gregg Bennett__ to see how to develop our design further from a professional packaging perspective. 

After discussing our project we found out that Gregg couldn't supply a custom housing for our PCB and instead would supply a larger generic box for us to work around. 

This was differnt than what we envisioned so we decided to move forward with the 3-D printing route for professional packaging

### Team Contract
As per assignment requirent, both Delilah and I completed the Team Contract Requiremnet.

This was a very good oppurtunity for both of us as it required us to sit down and discuss boundaries and expectations for how to progress in the future.

The summary of the contract is as below:

```
Each member is expected to finish their assigned work before meetings, show up on time, and communicate early if they are running late or struggling with workload. We also agreed that everyone should respond to messages within a reasonable time, be honest about their progress, and ask for help when needed instead of staying silent.

For project quality, everyone should review the work before submissions and give respectful, constructive feedback. Important progress and notes should be documented in the shared document so the whole team can stay updated. Overall, we want to work together most of the time, keep each other accountable, and make sure deadlines are not left to the last minute.

Even though both members will contribute to all parts of the project, each person has areas they are more familiar with. Idris will focus more on hardware, power, sensors, PCB design, sensor calibration, and microcontroller programming. Delilah will focus more on software, wireless communication, microcontroller programming, and user interface logic. Both members will also contribute equally to the writing assignments. The goal is to divide tasks based on strengths while still working together as a team.
```


### PCB Review

Since I was desinging the PCB for the first time, I wanted to make the deadline for PCB review.

My approach in the PCB design was as follows:

1. Follow the recommendations on the ESP32 website for component selection. This was to enure that the chips operate in nominal condition. [ESP Link](https://docs.espressif.com/projects/esp-hardware-design-guidelines/en/latest/esp32/schematic-checklist.html#schematic-checklist)
2. Use thicker wires for power delivary network to lower IR droop
3. Place capacitors near power supplies to avoid current/voltage supplies (in other words near the LDO)
4. Research on forums such as reddit to see find similar projects to see what component selection worked best with the chip
5. For the ESP I made a no-fill zone for the antenna to imporve signal integrity
5. Breakout as many pins to enable prototyping/debugging


Below is the PCB layout/schematic

![alt text](images/image-1.png)
![alt text](images/image-2.png)


