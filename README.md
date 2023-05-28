# JGA5Marlin
This is a repository containing the latest known functional firmware for the JGAroura/JGCreate A5

this repository exists as it took me 6 hours and about 30 attempts to update the firmware due to the fact that official support for this printer is effectely non existant and the official config files for marlin cause unexpected errors , this repository should allow an almost plug and play experiance

# How to flash the motherboard
Important: If you want to flash the main motherboard, then you MUST disconnect the 8-pin LCD module cable. Otherwise you may end up with a paperweight! Under the front edge of the printer is a hole, simply unplug the 8-pin cable before flashing.

Step 1: Software Installation & Source Code Download
Before you start, you need to download and install the following free software packages. Please note, there is NO need to install the Arduino IDE.
Marlin 2.0 firmware does not compile properly with the Arduino IDE any more.


1. Visual Studio Code (by Microsoft): https://code.visualstudio.com/download , 
2. Inside VS Code, install the Extensions "Platformio" and "Auto Build Marlin"

3. You may need to install the drivers for the CH340 Serial-to-USB chip used by the printer. This is to allow your computer to talk to the printer motherbaord.
a) PC CH340 serial drivers are here. https://sparks.gogo.co.nz/assets/_site_/downloads/CH34x_Install_Windows_v3_4.zip
b) Mac CH340 serial drivers are here. http://sampin.ch/ch340-driver-mac

Step 2: Compiling & Flashing
1. Open Visual Studio Code

2. Open Workspace, and open the folder "Motherboard Firmware"

3. Close ALL other programs that talk to the serial port. E.g. Cura, JGCreat, Pronterface, Simplify3D, etc.

4. Unplug the printer from Mains Power

5. Double check you have unplugged the LCD module cable -- the printer display should turn off, and should stay off for this entire operation.

6. Plug the printer into the computer via USB cable. you should hear a connection noise. The LCD on the printer should be off! If it is not, you have not unplugged the 8 pin cable 
DO THIS BEFORE PROCEDING OR YOU WILL BREAK THE LCD.

7. In Visual Studio code,  at the side of the window is a set of icons. Click the icon with a M in a box.
 ![image](https://github.com/joepotato04/JGA5Marlin/assets/52463691/e06c945c-eaab-44c3-b34a-4b7afdb1f01e)

 
8. you should now see a menu like this, press the button circled in red.


9. Wait. You will see the computer compile the firmware, and shortly afterward, it will upload the firmware to the printer.

10. You should see a success message. Once the process has completed,plug the rectangualar 8 pin connector back in. You have flashed the firmware successfully!

11. Run G-Code commands M502 (reset settings from firmware defaults) and M500 (save settings to EEPROM) after flashing. This can be done  manually using a program like Pronterface or the serial monitor in VS Code .alternatively download and place "reset.gcode" onto a usb stick ,"print" it, then after 30 seconds restart the printer using the switch on the back

12. you have now fully updated the Firmware on your 3D printer's Motherboard.



# How to Flash the LCD
The process for upgrading the firmware on the MKS LCD module (MKS-TFT28 v1.3):


![image](https://github.com/joepotato04/JGA5Marlin/assets/52463691/f9f99f05-8434-4fb1-8aac-ff2566592c4e)

1.Copy and paste the firmware files shown above to the root directory of an SD card.(root means not in any folders)
do not modify them unless you know what you are doing.


2.Turn the printer off

3.Insert the SD Card into the hidden slot inside the printer, on the back side of the LCD module. You may have to unplug the USB cable that goes to the screen in order to access it.

4.Turn the printer on, the firmware update will start automatically.

5. Once the firmware update is complete, the printer will start.

6. Turn the printer off

7. Remove the SD card

8. The files on the SD card will have been renamed, so if you leave the SD card inside and turn the printer on, it will not flash a second time.

9. Dont forget to plug the internal USB cable in again, if you disconnected it.

10. After flashing, the LCD may be set to look for files on the SD card only. You need to use the settings menu in the LCD to change this back to USB, otherwise your printer will not see any files when you plug in your USB!


# Troubleshooting
If you performed the LCD flash and now the LCD is only flashing “BOOTING” and beeping repeatedly - try flashing again with a different SD card, this is nothing to worry about , no harm has been done.

If you only see white squares on the LCD, you plugged the 8 pin connector into the wrong pins (the set you want is directly above the hole on the bottom front of the printer.

If you plug in a USB and you don't see any files, check the LCD settings page. There is an option for the LCD to look for files on SD card or on USB sticks. Also check you have plugged in the internal USB cable!
