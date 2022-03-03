# Neptune2_2SFirmwareMod
I wanted an updated look and feel of my Neptune 2S GUI. This is a new "theme", as well as enabling extra features such as PID tuning, switching to and from auto/manual bed leveling, adjusting steps, and custom filament preheat settings, as well as saving any/all changes to EEPROM. This is not a firmware update; it is only utilizing your current firmware.

Included are the files for both the Neptune 2 and 2S. Within each is the firmware config for stock, BLTouch/3dTouch, Wifi, and both BLTouch & Wifi. Choose your printer, then choose the upgrades you currently have. Throw both "elegoo_pics" and "elegoo.txt" on the sd card root and turn on your printer.

You can customize it further within the elegoo.txt file. Such settings such as PID autotuning is pre-set for 210c nozzle and 60c bed, but can be changed within that file. Same goes for filament preheats. Those commands can be found under the "moreitem" section:

moreitem_button1_cmd:M104 S210 E0;M140 S60; #preheat PLA

moreitem_button2_cmd:M104 S230 E0;M140 S80; #preheat PETG

moreitem_button3_cmd:G28 X0;G28 Y0;G1 X0 Y220 F3000;G4 P10000;G1 X0 Y75 F3000; #Clean bed. Bring bed out for 10 seconds, then retract

moreitem_button4_cmd:G28 X0;G28 Y0;G28 Z0;G1 X117 Y100 Z100 F3000;M303 E0 C5 S210 U1;M500;M303 E-1 C5 S60 U1;M500; #PID autotune. Will take a few minutes. Set to 210/60, my most common PLA temps. 5 cycles for both nozzle and bed

moreitem_button5_cmd:;

moreitem_button6_cmd:M500; #Save all configs to EEPROM
