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

We highly suggest you start with the Demo Mode first. To enter the demo mode, simply choose your vehicle, and on the OBD Adapter choice screen select "Demo Adapter".

The demo mode doesn't connect to a real vehicle, uses sample data and gives you a preview of functions and features specific to the selected model.

You can also start with `Connecting`_ to your vehicle (you will need one of the `compatible adapters`_).


********************
How to use JScan
********************

JScan is a quite straightforward application, but there are some basics you should understand before you connect to your car.

There are three main areas of the app:

	- Dashboard: with diagnostic and trail view functions
	- Modules: gives you access to *live data* of the vehicle's modules
	- Adaptation: lets you configure / reprogram your vehicle

See the details below.


Dashboard / Main screen
=======================

1) Quick Diagnostic - this screen is responsible for displaying "generic" - "check engine light" Trouble Codes

2) Live Data - this screen will dispay "generic" live data - live data that is common across multiple cars and models

Quick Diagnostic and Live Data available on main screen are generic (standard) data available on almost all cars and models to allow an independent technician to diagnose a car - this is how 99% of cheap OBD tools work

3) Advanced Scan - this is where fun begins - this screen will go through all modules available on the car and it will query about trouble codes

Modules
=======

This screen shows all possible modules for this model - it doesn't mean that are all actually installed on this particular car.

Each module has 3 functionalities:

1) Trouble Codes - this screen will allow you to show/clear - Trouble Codes on currently selected module

2) Live Data - this screen will allow you to show live data for currently selected module - you need to select pids/live data to start showing data for this module.

3) Activations -> This is a tab is for testing purpose - it alows you to test relays, bulbs, wipers etc.

Adaptations
===========

This screen will show all availalbe adaptations (configuration, settings changes) for this particular car.

Search button is available on bottom - we are trying to group related settings but this is not always possible.


************************
Free & Licensed features
************************

Free
====
Straight after installation JScan allows you to connect to your vehicle (as long as it is supported of course) and *read* the data from the ECU.
This means, that you can run a Quick Diagnostic but also take a look into ECU settings (via Adaptations) to see current values (for example wheel size, gear ratios, various features status etc.)

License
=======
What is a license for?
	License gives you the following additional functions:
	
	- Advanced Scan
	- Live data in specific modules
	- Trail View (for selected Vehicles)
	- Data modfication: **writing** to the ECU

For more details see the License section.

**********
Connecting
**********

You will need a compatible adapter. Check out the list of `compatible adapters`_.

For Wrangler JL, Gladiator JT and some other vehicles from 2018 onwards, you **will need a security bypass cable**. See details for each vehicle on our website and read the warning on the main screen of JScan app.


Bluetooth adapter
=================

.. note:: iPhones work with BT 4.0 (BLE) adapters only.

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
	.. note:: This is when the app store account license reads and locks the vehicle VIN, so if you connect to your mom's / dad's / friend's vehicle to show them how JScan works, you will bind the license to their VIN. There's no "undo".
7. Explore

.. note:: Hint: If you are having issues with connecting to the OBD Adapter please make sure that you gave all required permissions to the JScan app. This includes Location / GPS, and it has to be turned on in your phone. We DO NOT collect, store, or even use the location data in any way, but it has to be enabled dues to how mobile systems prviacy rules are built (in short: JScan needs to be *allowed to* to determine your location, because - in theory - it *could* do it based on the Wi-Fi or a BT device you are connected to).

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

.. _Connecting: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting