# Anycubic Kobra Neo Firmware with LCD Messaging

This is a fork of the publicly released Kobra Neo firmware version 1.3.3. It appears that newer firmwares from the vendor hinder the ability to output messages to the LCD.

Performining minor adjustments for quality of life improvements. Most of these are centered around Octoprint messaging functionality. I'm not sure why the vendor disabled these codes in newer firmwares.

- Enable M117 codes to allow Octoprint to send messages to the LCD (e.g. 'Heating ...' or 'Homing Z ...')
- Enable M73 codes to allow updating the LCD progress bar from Octoprint. This is usually a Percentage, with remaining time.
- Enable Quickhome
- Alter LCD menu and background colors
- Increase XYZ homing speed
- Speed up auto bed levelling
- Fix typos in messages text
- Square Wave Stepping is **not** enabled
- Linear Advance is **not** enabled
- version number will read 1.3.3a as a visual indicator of accepted firmware

This firmware contributes very little if anything to print quality.  If your prints are working as expected, and you're not looking to display slicer messages or allow Octoprint plugins to display custom messages, use the official firmware from Anycubic. 

## To Enable Code M73 in Cura
Go to Extensions -> Post Processing -> Modify G-Code and add 'Display Progress on LCD'.  Play with 'Time Remaining', 'M177 - All printers', and 'Percentage' until you get the appropriate output.  I turned everything 'on' in my slicer.

## To Enable Code M73 in Prusa/Superslicer
Under Expert Level Printer Settings, check the box next to 'Supports remaining times'

## Build instructions
https://www.reddit.com/r/anycubic/comments/y2waxu/tutorial_how_to_build_anycubic_marlin_source_code/

## Helpful Gcode Before and After Prints
I have another page with recommended Start and End Gcodes at [KobraNeoProfiles](https://https://github.com/sclebo05/KobraNeoProfiles). These codes handle warmup messaging (e.g. 'Heating'), calling the bed mesh, and printing an initial test line before jumping into the main print. They will improve quality of life for any firmware version of this printer.