# JGA5Marlin
This is a repository containing the latest known functional firmware for the JGAroura/JGCreate A5 ;this repository exists as it took me 6 hours and about 30 attempts to update the firmware due to various factors

# How to flash the motherboard
Important: If you want to flash the main motherboard, then you MUST disconnect the 8-pin LCD module cable. Otherwise you may end up with a paperweight! Under the front edge of the printer is a hole, simply unplug the 8-pin cable before flashing.

Step 1: Software Installation & Source Code Download
Before you start, you need to download and install the following software packages. Please note, there is NO need to install Arduino IDE any more. Marlin 2.0 firmware does not compile properly with the Arduino IDE any more.


1. Visual Studio Code: https://code.visualstudio.com/download , Inside VS Code, install the Extensions "Platformio" and "Auto Build Marlin"

2. You may need to install drivers for the CH340 Serial-to-USB chip used by the printer.
a) PC CH340 serial drivers are here.
b) Mac CH340 serial drivers are here.

Step 2: Compiling & Flashing
1. Open Visual Studio Code

2. Open Workspace, and Navigate to the outer Marlin folder created by Github desktop. (Not the inner marlin folder!) this will be something like ~/Documents/Github/JGA5Marlin/Motherboard Firmware

3. Close ALL other programs that talk to the serial port. E.g. Cura, JGCreat, Pronterface, Simplify3D, etc.

4. Unplug the printer from Mains Power

5. Double check you have unplugged the LCD module cable -- the printer display should turn off, and should stay off for this entire operation.

6. Plug the printer into the computer via USB cable. The LCD on the printer should be off! If it doesn't, you have not unplugged the cable in step 15.

7. In Visual Studio code,  at the side of the window is a set of icons. Click the icon with a M in a box.
 ![image](https://github.com/joepotato04/JGA5Marlin/assets/52463691/e06c945c-eaab-44c3-b34a-4b7afdb1f01e)

 
8. you should now see a menu like this, press the button circled in red.


9. Wait. You will see the computer compile the firmware, and shortly afterward, it will upload the firmware to the printer.

10. You should see a success message. Once the process has completed, unplug the printer from the computer, and plug the printer display back in. You have flashed the firmware successfully!

11. It is highly recommended to run G-Code commands M502 (reset settings from firmware defaults) and M500 (save settings to EEPROM) after flashing. This can be done  manually using a program like Pronterface, or the serial monitor in VS Code .Or, you can make a text file, place M502 and M500 on sequential lines, save the file as "reset.gcode", transfer the file to the printer and then "print" this file.
