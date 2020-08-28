###############
Getting Started
###############

************
Installation
************
You can install the JScan app via Apple Appstore or Google Play, free of charge.

Free stuff & Licenses
=====================

Free
^^^^
Straight after installation JScan allows you to connect to your vehicle (as long as it is supported of course) and *read* the data from the ECU.
This means, that you can run a Quick Diagnostic but also take a look into ECU settings to see current values (for example wheel size, gear ratios, various features status etc.)

Demo
^^^^
You can explore JScan feature *without* connecting to an actual vehicle. Just start on step 4 in `Connecting`_ and choose "Demo adapter" in step 6.

Want to learn about `my favorite programming language`_?

.. _my favorite programming language: http://www.python.org

License
^^^^^^^
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

**********
Connecting
**********
TODO: describe connecting process
Bluetooth adapter:

1. Plug the adapter into the OBD port
	In newer vehicles (2018+) you might need to use a security bypass cable in order to make changes to your vehicle. See the vehicle-specific section.

2. **Turn the key to ON/RUN position**
	.. caution::   The dashboard controls need to light up, basic checks need to be performed.

				ACC position is not enough.

				You *can* connect to your vehicle with engine running but **don't** make any adaptations.

3. To connect with the vehicle via a Bluetooth adapter:
	- on Android: pair the BT adapter with the phone, according to the adapter's manual
	- on iOS: only OBD MX+ adapter needs pairing with the phone. If you use any other adapter, skip this step

4. Open JScan app
5. Select your vehicle
6. Select your adapter
7. Explore

Troubleshooting
---------------
TODO: What to do when...




Step-by-step Guide
------------------
This is a high-level guide about how to change a setting in your vehicle:

1. Find JScan in your app store
2. Install JScan
3. Purchase a license (from within the app)
4. Connect to your vehicle
	This is when the app store account license reads and locks the vehicle VIN, so if you connect to your mom's / dad's / friend's vehicle to show them how JScan works, you will bind the license to their VIN. There's no "undo".
5. Go to Adaptation section
6. Find the setting you want to change
7. Provide a new value and tap the "GO" button.