###############
Troubleshooting
###############

General connectivity issues
===========================

.. attention:: Do NOT purchase the license as a “fix". The license has nothing to do with the communication between the devices.

If the connection is established, but JScan features don't work (App can't read VIN, adaptations fail, etc.) it is usually an issue with the adapter, especially if it's a cheaper one.

OBD Adapter check
-----------------

Go to JScan settings and tap on *ELM327 Identification*.

- If every row reports TRUE (green) then the adapter is most likely fine, and everything should work. Make sure you have selected a correct vehicle, that you have a license, the key is in RUN etc.
- If any row reports FALSE (red) then there is a communication issue:
	- All rows except the last one (ABS) are testing the communication between your phone and the adapter. Any issues here indicate an unsupported or malfunctioning adapter. Replace the adapter.
	- The last row - ABS - is an adapter-vehicle communication problem. There are multiple possible reasons:
		* The car is not turned on (set the key to RUN, not ACC)
		* The socket connection is bad (check the pins)
		* The adapter is faulty (replace the adapter)
		* Other, unknown causes - get in touch with us


Connection lost - You will be disconnected from: Bluetooth
----------------------------------------------------------

If you are getting the error above, please uninstall Torque application.


Other issues
------------

Other common reasons include:
	- no bypass cable in a vehicle that requires it
	- incorrect adapter choice in the list
	- incorrect vehicle choice in the list
	- another diagnostic application using the BT connection (yes, they do it even when not running - they work in the background)

.. note:: If you're facing any other issue, or the problem solutions described above don't work - get in touch with us on FB messenger. We will figure this out. Please include the vehicle model & year, adapter brand, phone OS (Android or iOS) and what steps you took.


JScan doesn't read the VIN
==========================

	1. Make sure the key is in ON position (not ACC) – i.e. dashboard controls are on.
	2. Inspect the OBD adapter and socket. Do pins fit tight? Or are they loose / dirty / rusty / broken?
	3. Go to JScan settings (cog, top-right corner) > ELM327 identification. All entries except ABS are adapter-phone communication. ABS is adapter-car. Any “false" values will indicate a possible adapter issue.
	4. If it’s a new purchase use “Return and Replace" or similar method to get another device from the vendor.

Tire Size adaptation
====================

Check engine light is on and speedometer not working.

	Was the adaptation done with engine working?

	If yes, open “Quick Diagnostic" page and tap “Trash" icon. Engine must be OFF and Ignition must be ON (usually second key position). All should be back to normal.

	If not, (that is, if adaptation was done with key ON, engine OFF), you probably typed the tire size manually. However, the manual input here is for circumference (in mm), NOT the diameter (height). So, either do the math (tire height inches * 2.54 * PI) and type the result in manual input, or – recommended – use the drop down to find the closest value matching tire height (in).

	.. note:: Factory speedometer is ALWAYS showing higher reading than you actually drive. That’s a safety feature, required legally for example in the EU. If you want to ‘fix’ it, just pick a slightly smaller tire height (0.25"-0.5" less than real).

Check engine and / or ABS fault is on.
	
	The new tire size is outside of an acceptable range. Some vehicles (more 'civilian') have a hard-coded limit of a tire size.