# klipper-dgus_CR6_from_Vyper
A project to port klipper-dgus to the CR6 DWIN T5L 272x480 display and extend/modify that project for my personal use.
The latest release posted here is functional and stable when installed and configured per the documentation, on a CR6 printer

## Background
At the time I first created this fork (Nov 2022):

* I was already able to use Klipper to control my CR6-SE printer, but:
  * Klipper could not communicate with the T5L 272x480 display connected to that printer.  My CR6 DWIN display was therefore literally useless, when I was running Klipper on the mainboard. 
  * to interact with Klipper while physically at the printer and away from my laptop running Mainsail, I instead connected an HDMI LCD touchscreen to my Klipper mcu (pi 3b+) and ran KlipperScreen.

* The [developer (Sebastian Holzgreve)](https://github.com/seho85) of klipper-dgus and python-dgus has:
  * solved the technical challenge of establishing a bi-directional real-time communications link between a DWIN TFT display running DGUS2 apps coded with DGUSTool 8.2.1.14 and Klipper (via the Moonraker API) on the AnyCubic Vyper DGUS T5L 480x762 display.
  * released [the python-dgus library](https://github.com/seho85/python-dgus) and [his (Anycubic Vyper) klipper-dgus project](https://github.com/seho85/klipper-dgus), under the [GPLv3 license](https://github.com/seho85/python-dgus/blob/master/License), thus enabling their installation and reuse by similar projects such as this one. (Thank you!)

## My Goals for This Project
1. My first goal for this project was to port the existing (Nov 2022) Anycubic klipper-dgus solution to run on the CR6 DWIN T5L 272x480 displays, to restore some level of functionality to my CR6 DWIN display, while running Klipper. 
   - As of 7Nov22:
     - I achieved this goal, by doing the following: 
       - installed python-dgus per the online instructions, 
       - re-sized all of the bitmap files from klipper-dgus to 272x480 pixels
       - created a new project in DGUSTool 8.2.1.14, adding the resized images and importing the overlays from the klipper-dgus DWIN-SET folder
       - edited the control and display objects to work with the new screens
       - generated the new 32.icl,40.icl and 42.icl files
       - saved and generated the new DWIN_SET 13, 14, and 22.bin files
       - modified the CR6Community DWIN_SET file T5LCFG_272480.CFG to load the menu screens from 32.icl instead of 22.icl
       - renamed the modified T5LCFG file to T5LCFG_272480K.CFG and copied that to the new DWIN_SET folder
       - copied the CR6Community FONT file 0_DWIN_ASC.HZK to the new DWIN_SET folder (to ensure that the CR6Community Firmware font is the one used for all text messages displayed on the flashed screen (planning to modify the screen bitmaps to use that same font, in a future release)
       - zipped the DWIN_SET file as Klipper-dgus_CR6_DWIN_SET_v0.7.zip to facilitate DWIN_SET downloads from GitHub
       - extracted and flashed the DWIN_SET folder from Klipper-dgus_CR6_DWIN_SET_v0.7.zip to my CR6 display
     - I continued also running KlipperScreen and Mainsail, to access controls and data still not available on the CR6 display

2. My second goal was to use the ported display screens while printing on my CR6-SE, comparing the functionality with that of KlipperScreen and of the CR6Community Firmware, and noting any "user experience" issues that I have with the current system.
   - I achieved this goal in Nov 2022.
 
3. My third goal was to understand the existing python-dgus library and klipper-dgus software architecture well enough to be able to modify and extend the functionality of the DWIN display screens in ways that remain consistent and compatible with the python-dgus library.
    - In Nov/Dec 2022, I was able to edit existing functions, but I did not learn how to extend the UI with new functions of my own.
    - I then moved over to [the DGUS-Reloaded for CR-6 project](https://github.com/Thinkersbluff/DGUS-Reloaded_for_CR6-DWIN-SET_Component) and suspended my activities here.
  
4. My fourth goal was to collaborate with Sebastian, when extending and/or deviating from his klipper-dgus design, to remain consistent and compatible with his python-dgus library (which is partly structured around the implemented structure and functionality of his klipper-dgus display screens)
    - That goal remains aspirational, but I have focused all of my activities to-date on the DGUS-Reloaded project, since Dec 2022.
  
5. My fifth goal is to learn enough about python programming, DGUS/DWIN serial communications, DWIN screen development, Moonraker API, Klipper Printer Objects, and Sphinx documentation, to be able to contribute valid and useful Pull Requests to the upstream python-dgus project.
     - This goal is aspirational.  It is also suspended indefinitely, since Dec 2022.

