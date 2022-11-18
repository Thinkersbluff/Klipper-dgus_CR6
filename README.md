# klipper-dgus_CR6_from_Vyper
A project to port my klipper-dgus_Vyper project fork to the CR6 DWIN T5L 272x480 display and extend/modify that project for my personal use.

## Background
As I create this fork (Nov 2022):

* I am already able to use Klipper to control my CR6-SE printer, but:
  * Klipper can not communicate with the T5L 272x480 display connected to that printer.  My CR6 DWIN display is therefore literally useless, when I am running Klipper on the mainboard. 
  * to interact with Klipper while physically at the printer and away from my laptop running Mainsail, I must instead connect an HDMI LCD touchscreen to my Klipper mcu (pi 3b+) and run KlipperScreen.

* The [developer (Sebastian Holzgreve)](https://github.com/seho85) of klipper-dgus and python-dgus has:
  * solved the technical challenge of establishing a bi-directional real-time communications link between a DWIN TFT display running DGUS2 apps coded with DGUSTool 8.2.1.14 and Klipper (via the Moonraker API) on the AnyCubic DGUS T5L 480x762 display.
  * released [the python-dgus library](https://github.com/seho85/python-dgus) and [his (Anycubic Vyper) klipper-dgus project](https://github.com/seho85/klipper-dgus), under the [GPLv3 license](https://github.com/seho85/python-dgus/blob/master/License), thus enabling their installation and reuse by similar projects such as this one. (Thank you!)

## My Goals for This Project
1. My first goal for this project was to port the existing (Nov 2022) Anycubic klipper-dgus solution to run on the CR6 DWIN T5L 272x480 displays, to restore some level of functionality to my CR6 DWIN display, while running Klipper. 
   - As of 7Nov22:
     - I have achieved this goal (using Klipper-dgus_CR6_DWIN_SET_v0.7.zip)
     - I am also running KlipperScreen and Mainsail, to access controls and data still not available on the CR6 display

2. My second goal is to use the ported display screens while printing on my CR6-SE, comparing the functionality with that of KlipperScreen and of the CR6Community Firmware, and noting any "user experience" issues that I have with the current system.
   - This goal is currently process.
 
3. My third goal is to understand the existing python-dgus library and klipper-dgus software architecture well enough to be able to modify and extend the functionality of the DWIN display screens in ways that remain consistent and compatible with the python-dgus library.
    - This goal is currently in process.
  
4. My fourth goal is to collaborate with Sebastian, when extending and/or deviating from his klipper-dgus design, to remain consistent and compatible with his python-dgus library (which is partly structured around the implemented structure and functionality of his klipper-dgus display screens)
    - This goal is currently in process.
  
5. My fifth goal is to learn enough about python programming, DGUS/DWIN serial communications, DWIN screen development, Moonraker API, Klipper Printer Objects, and Sphinx documentation, to be able to contribute valid and useful Pull Requests to the upstream python-dgus project.
     - This goal is aspirational.  It is also in process...

