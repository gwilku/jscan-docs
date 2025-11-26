
.. attention:: Do NOT purchase the license as a “fix". The license has nothing to do with the communication between the devices.

.. note:: iPhones work with BT 4.0 (BLE) or newer adapters only.

First steps:
============


1. Make sure the key is in RUN, not ACC position.
2. Make sure you are using a supported adapter (check the list of `compatible adapters`_).
3. Make sure your phone has Bluetooth or Wi-Fi enabled (depending on the adapter type).
4. Make sure you gave JScan all required permissions
5. Make sure you **choose the correct adapter** from the list

.. note:: The *Auto-connect* option is for BT 4.0 (BLE) devices only, and they should be used with the *auto-connect* only

6. Make sure no other OBD applications are using the adapter (and uninstall Torque, it works in the background preventing JScan from connecting)
7. Make sure you **choose the right vehicle model**. The year ranges are there for a reason


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

	1. Wait. As the error advises: **WAIT** a few seconds on the main screen before moving on to other app sections. The VIN should appear at the top of the main screen.

If the above doesn't help:

	2. Make sure the key is in ON position (not ACC) – i.e. dashboard controls are on.
	3. Inspect the OBD adapter and socket. Do pins fit tight? Or are they loose / dirty / rusty / broken?
	4. Go to JScan settings (cog, top-right corner) > ELM327 identification. All entries except ABS are adapter-phone communication. ABS is adapter-car. Any “false" values will indicate a possible adapter issue.
	5. If it’s a new purchase use “Return and Replace" or similar method to get another device from the vendor.

You may also try specifying explicitly, which module you want to query for the VIN. Go to JScan settings > App and adapter settings > scroll to the end, and change the value in Alternative VIN Source. The available options are:

- TCM
- PCM
- ABS
- RFH
- BCM
- WCM
- TIPCGW



Connection lost - You will be disconnected from: Bluetooth
==========================================================

If you are getting the error above, please uninstall Torque, OBDLink or any other OBD application.
If you don't have them installed, but are still getting this error please contact us.


Other issues
============

Other common problem include:
	- no bypass cable in a vehicle that requires it (2018+)
	- incorrect adapter choice in the list
	- incorrect vehicle choice in the list (especially tricky with WK2 2014 - make sure you choose the correct pre- or post-lift model)
	- another diagnostic application using the BT connection (yes, they do it even when not running - they work in the background)

.. note:: If you're facing any other issue, or the problem solutions described above don't work - get in touch with us on FB messenger. We will figure this out. Please include the vehicle model & year, adapter brand, phone OS (Android or iOS) and what steps you took.