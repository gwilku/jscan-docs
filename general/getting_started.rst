###############
Getting Started
###############

************
Installation
************
You can install the JScan app via Apple Appstore or Google Play, free of charge.

First steps & DEMO mode
=======================
After installation you can immediately start using JScan.

You can either:

	- Start with `Connecting`_ to your vehicle
	- Play with sample data in a demo mode (follow the steps for `Connecting`_ and choose "Demo adapter" in step 6)

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
============================================
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

For Wrangler JL, Gladiator JT and some other vehicles from 2018 onwards, you **will need a security bypass cable**. See details for each vehicle on our website and read the warning on the main screen of JScan app.


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


.. Want to learn about `my favorite programming language`_?

.. _my favorite programming language: http://www.python.org

.. _compatible adapters: http://jscan.net/supported-and-not-supported-obd-adapters/

.. _security bypass: http://jscan.net/jl-jt-security-bypass/