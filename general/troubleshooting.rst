########################
|:bulb:| Troubleshooting
########################

******************************************
Troubleshooting connection issues
******************************************

.. attention:: Do NOT purchase the license as a “fix". The license has nothing to do with the communication between the devices.

First steps:
============


1. Make sure the key is in RUN, not ACC position.
2. Make sure you are using a supported adapter (check the list of `compatible adapters`_).
3. Make sure your phone has Bluetooth or Wi-Fi enabled (depending on the adapter type).
4. Make sure you gave JScan all required permissions
5. Make sure you **choose the correct adapter** from the list

... note::	The *Auto-connect* option is for BT 4.0 (BLE) devices only.

6.Make sure no other OBD applications are using the adapter (and uninstall Torque, it works in the background preventing JScan from connecting)


If the connection is established, but JScan features don't work (App can't read VIN, adaptations fail, etc.) it is usually an issue with the adapter, especially if it's a cheaper one.

OBD Adapter check
=================

Go to JScan settings and tap on *ELM327 Identification*.

- If every row reports TRUE (green) then the adapter is most likely fine. It means it is responding to basic OBD commands (it does not mean that it's capable of performing all adaptations though - again, check the list of supported adapters).
- If any row reports FALSE (red) then there is a communication issue:
	- All rows except the last one (Module) are testing the communication between your phone and the adapter. Any issues here usually indicate an unsupported or malfunctioning adapter. Replace the adapter.
	- The last row - Module - is an adapter-vehicle communication problem. There are multiple possible reasons:
		* The car is not turned on (set the key to RUN, not ACC)
		* The socket connection is bad (check the pins 6 & 14 for OBD2 network connectivity)
		* The adapter is faulty (replace the adapter)
		* Other, unknown causes - get in touch with us


JScan doesn't read the VIN
==========================

	1. Make sure the key is in ON position (not ACC) – i.e. dashboard controls are on.
	2. Inspect the OBD adapter and socket. Do pins fit tight? Or are they loose / dirty / rusty / broken?
	3. Go to JScan settings (cog, top-right corner) > ELM327 identification. All entries except ABS are adapter-phone communication. ABS is adapter-car. Any “false" values will indicate a possible adapter issue.
	4. If it’s a new purchase use “Return and Replace" or similar method to get another device from the vendor.

You may also try specifying explicitly, which module you want to query for the VIN. The available options are:

- TCM
- PCM
- ABS
- RFH
- BCM
- WCM
- TIPCGW



Connection lost - You will be disconnected from: Bluetooth
==========================================================

If you are getting the error above, please uninstall Torque application.
If you don't have Torque, but are still getting this error please contact us.


Other issues
============

Other common problem include:
	- no bypass cable in a vehicle that requires it (2018+)
	- incorrect adapter choice in the list
	- incorrect vehicle choice in the list (especially tricky with WK2 2014 - make sure you choose the correct pre- or post-lift model)
	- another diagnostic application using the BT connection (yes, they do it even when not running - they work in the background)

.. note:: If you're facing any other issue, or the problem solutions described above don't work - get in touch with us on FB messenger. We will figure this out. Please include the vehicle model & year, adapter brand, phone OS (Android or iOS) and what steps you took.


******************************************
Troubleshooting license purchase issues
******************************************

If you run into problems when purchasing the license, first of all **read** the error message. It usually provides an explanation of what the problem is:

	- No network connection issue:
		- make sure you are connected to the web, and **disconnect** from a Wi-Fi cast by the adapter
		- make sure that you have granted JScan all the required permissions: that includes Location / GPS, and make sure GPS is actually enabled. **We do not use or collect this data.** However a connectivity framework on mobile phones is build in a way taht requires these permissions.

	- Item already owned error:
		- this can happen if you bought your first licence before 2020, when we introduced account tokens and decoupled the licenses from your Apple/Google ID, and you are trying to buy another license.
		- go to JScan settings > Manage Licenses & Account > Status
		- write down your account token if present
		- tap the green icon (...) and select > "Consume all in-app purchases"
		- close JScan (completely, not just drop to background with the Home button)
		- open JScan again and try buying the license
		- if it still doesn't work, restart the phone
		


******************************************
Troubleshooting specific adaptations
******************************************


Tire size issues:
======================

Check engine light is on and speedometer not working:

	Was the adaptation done with engine working? Have you started the vehicle immediately after making the adaptation (without turning it off first)?

	If yes, open “Quick Diagnostic" page and tap “Trash" icon. Engine must be OFF and Ignition must be ON (usually second key position). All should be back to normal.

	If not, (that is, if adaptation was done with key in RUN, engine OFF), you probably typed the tire size manually. However, the manual input here is for circumference (in mm), NOT the diameter (height). So, either do the math (tire height inches * 2.54 * PI) and type the result in manual input, or – recommended – use the drop down to find the closest value matching tire height (in).

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


*******************
Test Area |:bulb:|
*******************

This should be a bulb: |:bulb:| and an exclamation |:exclamation:|

This is a manually placed Unicode bulb, causing PDF generation to crash: 💡




.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting

.. _compatible adapters: http://jscan.net/supported-and-not-supported-obd-adapters/