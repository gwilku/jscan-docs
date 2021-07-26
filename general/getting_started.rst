###############
Getting Started
###############

************
Installation
************
You can install the JScan app via Apple Appstore or Google Play, free of charge.

First steps & DEMO mode
=======================
After installation you can immediately start using JScan. No car neededed, no license required.

How? Simple - just use the Demo mode: Start at step 4 in `Connecting`_ and choose "Demo adapter" in step 6.

You can also start working with your car - see `Connecting`_

************************
Free & Licensed features
************************

Free
====
Straight after installation JScan allows you to connect to your vehicle (as long as it is supported of course) and *read* the data from the ECU.
This means, that you can run a Quick Diagnostic but also take a look into ECU settings to see current values (for example wheel size, gear ratios, various features status etc.)

License
=======
What is a license for?
	License gives you the following additional functions:
	
	- Advanced Scan
	- Live data in specific modules
	- Trail View (for selected Vehicles)
	- Data modfication: **writing** to the ECU

How does license work?
	A license is a slot for 1 VIN. It's attached to your account token (found in settings > Manage Licesnses & Account > Status). You can use this token to use JScan on multpile devices (with the same vehicle). Just install JScan on another phone or tablet and type the token in the settings - both devices will use the same license.

	If you sell your vehicle, you can pass the account token to the new owner, clear it from your phone and get yourself a new license for your new vehicle (this will also generate a new token for you to use).

	If you have multiple licenses used under the same token and want to pass only one of them when selling the car, please contact us via Facebook message.

Can I transfer my license to another device?
	Short answer: Yes. In late 2020 we introduced a new licensing system.

	- On your current device go to Settings > Manage Licenses > Status. You will see a yellow field with a 6-character token there
	- On your new device, go to the same place and tap the token button (it should say "Add") and type the token in
	- Tap refresh icon and/or restart the app if necessary

	.. note:: If there's no token on your old device or you are experiencing other license issues, please get in touch with us.

How do I buy a license?
	When connecting to a new vehicle, you will be prompted if you want to assign a license to the vehicle, or if you want to buy a license if you do not have one. This is the most common way.

	The second way of obtaining a license is entering settings (gear icon in top right corner) -> “manage licenses". In this screen you can buy a license to assign it later during connection. Note that this is the only way of obtaining a license if you are using a WiFi adapter, as on most phones you will not be able to access the internet while connected to the adapter’s WiFI network.

I bought a license, but nothing happened!!! What next?!
=======================================================
	Almost correct. You can check in Settings > Manage Licenses & Account > Status if the number of purchased licenses increased. If yes (if you have more "Purchased" than "Used" licenses) just connect to your vehicle (see below). That's it. Although we recommend reading the documentation first. It will really save a lot of trouble in future.


**********
Connecting
**********

You will need a compatible adapter. Check out the list of `compatible adapters`_.

For Wrangler JL, Gladiator JT and possibly some other vehicles from 2018 onwards, you will need a security bypass cable. See details for each vehicle on our website and read the warning on the main screen of JScan app.


Bluetooth adapter
=================

1. Plug the adapter into the OBD port
	In newer vehicles (2018+) you might need to use a `security bypass`_ cable in order to make changes to your vehicle. See the vehicle-specific section.

2. **Turn the key to ON/RUN position**
	.. caution::   The dashboard controls need to light up, basic checks need to be performed.

				ACC position is not enough.

				You *can* connect to your vehicle with engine running but **don't** make any Adaptations unless they are explixitly designed for it. It's fine to use Trail View, read Live Data, etc.

3. To connect with most modern OBD Adapters there is **no need to pair them with the phone first**. You might need it with older devices (BT 3.0 & 2.0), but try without pairing first.
4. Open JScan app
5. Select your vehicle
6. Select "Autoconnect" if your adapter is listed in the option's description, or choose your proper BT adapter (note, that there are separate groups for 4.0 BLE and 3.0 & older BT adapters, make sure you tap the correct option)
7. Explore

.. note:: Hint: If you are having issues with connecting to the OBD Adapter please make sure, that you gave all required permissions to the JScan app. This includes Location / GPS, and it has to be turned on in your phone. We DO NOT collect, store, or even use the location data in any way, but it has to be enabled dues to how mobile systems prviacy rules are built (in short: JScan needs to be *allowed to* to determine your location, because - in theory - it *could* do it based on the Wi-Fi or a BT device you are connected to).

Wi-Fi adapter
=============

Follow the steps above, but at step 3.

	- connect to a Wi-Fi cast by the adapter
	- some adapters and phones will require you to disable mobile data transfer, otherwise the connection will fail
	- make sure you allow JScan to use your device location - it's needed for establishing the wi-fi connection (see note above)

**************
Making Changes
**************

This is a high-level guide about how to change a setting in your vehicle:

1. Find JScan in your app store
2. Install JScan
3. Purchase a license (from within the app)
4. Connect to your vehicle
	This is when the app store account license reads and locks the vehicle VIN, so if you connect to your mom's / dad's / friend's vehicle to show them how JScan works, you will bind the license to their VIN. There's no "undo".
5. Go to Adaptation section
6. Find the setting you want to change
7. Choose a new value and tap the "GO" button.




******************************************
Troubleshooting connection issues
******************************************

.. attention:: Do NOT purchase the license as a “fix". The license has nothing to do with the communication between the devices.

First steps:
------------

1. Make sure the key is in RUN, not ACC position.
2. Make sure you are using a supported adapter.
3. Make sure your phone has Bluetooth or Wi-Fi enabled (depending on the adapter type).
4. Make sure you *choose the correct adapter* from the list
	Auto-connect is for BT 4.0 (BLE) devices only.

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






.. Want to learn about `my favorite programming language`_?

.. _my favorite programming language: http://www.python.org

.. _compatible adapters: http://jscan.net/supported-and-not-supported-obd-adapters/

.. _security bypass: http://jscan.net/jl-jt-security-bypass/