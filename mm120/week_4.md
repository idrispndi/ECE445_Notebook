# WEEK 4

    Author: Idris Ispandi
    March 2 2026


### New Teammate Addition

At this week we added a new teammate __Charis Wang__. She  mentioned that her background is in Power so we agreed that she will be responsible for ensuring the Power Delivary Network for the 3.7V and 5V motor is stable.

### Design Review

To ensure that our design was robust we had a meeting with Professor __Viktor Gruev__ and TA __Mingrui Liu__ to present our design document. Below were the key feedback

1. Viktor requested we explore what is the current draw of the motor at startup as an additional constraint

2. Explore the Idea of proximity detection( if not within certain distance of a node the motor won't activate).

We took into account the first point into our overall design approach. For the sencond point we as a team agreed to implement it if time permits.

### Second Round PCB

After Some research Charis said that she found a suitabl candidate for and LDO that could help supply stable 3.3V to the ESP32 from a 3.7V LiPO battery. This was incorporate in the Design and was packaged and sent as a gerber file.

![alt text](secondround_sensornode.png)