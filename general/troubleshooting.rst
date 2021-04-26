###############
Troubleshooting
###############

Tire size issues:
======================

Check engine light is on and speedometer not working:

	Was the adaptation done with engine working?

	If yes, open “Quick Diagnostic" page and tap “Trash" icon. Engine must be OFF and Ignition must be ON (usually second key position). All should be back to normal.

	If not, (that is, if adaptation was done with key ON, engine OFF), you probably typed the tire size manually. However, the manual input here is for circumference (in mm), NOT the diameter (height). So, either do the math (tire height inches * 2.54 * PI) and type the result in manual input, or – recommended – use the drop down to find the closest value matching tire height (in).

	.. note:: Factory speedometer is ALWAYS showing higher reading than you actually drive. That’s a safety feature, required legally for example in the EU. If you want to ‘fix’ it, just pick a slightly smaller tire height (0.25"-0.5" less than real).

Check engine and / or ABS fault is on:
	
	The new tire size is outside of an acceptable range. Some vehicles (more 'civilian') have a hard-coded limit of a tire size.


Gear ratio issues:
======================

After changing the gear ratio the vehicle goes int limp mode and "incorrect gear ratio" error appears in Advanced scan:
	
	Make sure you set the correct gear ratio (we've heard about mis-labeled gear sets)
	If the ratio is fine, make sure you followed the correct procedure. If not - repeat it.


Troubleshooting DRLs
====================

Check your Daytime running lights On/Off, this option should be set to Active

.. image :: ../img/DRL-OnOff.png
	:width: 200 px	

Check DRL Voltage Regulation Left & Right to make sure there is power set to:

	- 5.0 V or 7.0 V for classic bulbs if you want them to shine at 50% power
	- *12.4 V for LEDs* or full power from regular bulbs

Those settings are available under Lights Voltage Regulation

.. image :: ../img/DRL-Voltage.png
	:width: 200 px	
