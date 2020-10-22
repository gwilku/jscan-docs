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
	- Trail View (for selected Vehicles)
	- Data modfication: **writing** to the ECU

How does license work?
	A license is basically a product attached to your app store account. Each license has a slot for the VIN, which gets assigned upon the first connection to the vehicle.

Can I transfer my license to another device?
	Short answer: no.

	Longer answer: no, but you can use the same license on multiple devices (phone / tablet) as long as they all use the same app store account and you connect to the same vehicle.

	If you're changing a phone from Android to iOS or vice versa and whish to continue using JScan with the same vehicle - please get in touch with us on messenger.

How do I buy a license?
	When connecting to a new vehicle, you will be prompted if you want to assign a license to the vehicle, or if you want to buy a license if you do not have one. This is the most common way.

	The second way of obtaining a license is entering settings (gear icon in top right corner) -> “manage licenses". In this screen you can buy a license to assign it later during connection. Note that this is the only way of obtaining a license if you are using a WiFi adapter, as on most phones you will not be able to access the internet while connected to the adapter’s WiFI network.

**********
Connecting
**********

You will need a compatible adapter. Check out the list of `compatible adapters`_.


Bluetooth adapter
=================

1. Plug the adapter into the OBD port
	In newer vehicles (2018+) you might need to use a security bypass cable in order to make changes to your vehicle. See the vehicle-specific section.

2. **Turn the key to ON/RUN position**
	.. caution::   The dashboard controls need to light up, basic checks need to be performed.

				ACC position is not enough.

				You *can* connect to your vehicle with engine running but **don't** make any Adaptations unless they are explixitly designed for it. It's fine to use Trail View, read Live Data, etc.

3. To connect with the vehicle via a Bluetooth adapter:
	- on Android: pair the BT adapter with the phone, according to the adapter's manual
	- on iOS: only OBD Link MX+ adapter needs pairing with the phone. If you use any other adapter, skip this step

4. Open JScan app
5. Select your vehicle
6. Select your adapter
7. Explore

Wi-Fi adapter
=============

Follow the steps above, but at step 3.

	- connect to a Wi-Fi cast by the adapter
	- some adapters and phones will require you to disable mobile data transfer, otherwise the connection will fail


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








.. Want to learn about `my favorite programming language`_?

.. _my favorite programming language: http://www.python.org

.. _compatible adapters: http://jscan.net/supported-and-not-supported-obd-adapters/