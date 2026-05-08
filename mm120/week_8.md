# WEEK 8

    Author: Idris Ispandi
    March 30 2026

### PCB soldering 
I had worked on soldering the PCB over the weekend and finally got all the components on the first round PCB.

Upon plugging it I the ESP32 was showing up periodically. Intially I though that this was a buggy ESP. AS there was no way for me to monitor what data transfaer was happening without a logic analyzer. 

Therefore I moved on to the 2nd round PCB. This one was slightly easier as we had a mask for it. It took a few iterations still as I had a few notable issues:

1. Oven not hot enough - lead to solder paste not melting properly
2. Spreading too much solder paste cause some short which later had to be fixed using heat gun/ soldering iron.

After completing the second round I plugged the board in and still got the same issue where the ESP32 was blinking on the COM port. 

I explored the [forums](https://www.reddit.com/r/esp32/comments/ivtdzf/esp32_keeps_disconnecting_and_reconnecting_from/) and youtube for this issue and came up with a fix to make it stable.


The fix was too make press the EN and RST LOW before plugging. The datasheet mentions that this forces the flash mode so the ESP appears stable at the terminal.

Afterwords I programmed to test that a program can be flashed and blinky worked.

The day after I was using a different cable that was longer and it was unable to program it. I swithed to a shorter one and it worked. My conclusion was the on board traces were poorly matched leading to too mcuh of a signal differential at output causing the board to be not be seen.

These finding were captured in the individual progress report


### Individal Progress Report
*see report for more details

### PCB arrival

We also received the 3rd round PCB this week and Charis worked on those boards. I conveyed to her my known bugs as it was likely she would encounter them.




