######################
Key Programming - BETA
######################

.. attention:: Both key programming and this documentation section are *work in progress*. That means it might or might not work, the process and details described might be inaccurate, etc. You have been warned.


Foreword
=================================

JScan has the capability of adding a new key to a list of keys accepted by the vehicle, **HOWEVER** this is still a work-in-progress feature, a **BETA, EXPERIMENTAL FEATURE** if you will. We cannot guarantee it will work for your particular vehicle and - what's more important - for a particular key / fob. In addition, there is a lot of external factors that can interfere with the coding process and they are beyond JScan control. We cannot provide individual support for key programming issues.

Requirements
=================================

The following are a must:

	- a Bluetooth Adapter - it **will not work** with a wi-fi OBD device
	- internet connection (either via wi-fi or mobile data)

Recommended:

	- an OEM key that mathces the original key part number - aftermarket keys might or might not work, even from the same supplier
	- a new battery in the fob - or at least check the battery voltage; with flat battery the buttons will surely not work	

How to program a key
====================

	.. note:: 
	To determine, which WCM your vehicle is equipped with, see the hint in the adaptation, or follow these steps:

	Go to Modules section, open either RFH (Radio Frequency Hub) or WCM (Wireless Control Module / Wireless Control TPMS)

	Check Active Diagnostic Variant (RFH) or Variant ID (WCM) value. This is the identifier of the module responsible for handling the key IDs.

1. Acquire a vehicle PIN. To do it via JScan:

	- `Connect`_ to your vehicle using your current key
	- Open Adaptations
	- Find "PIN Reading - BETA" or similarly named adaptation (use the search)
	- From the dropdown list choose an appropriate WCM (see models listed in brackets on the dropdown list)
	- *RUN THE PROCEDURE* - the initially displayed PIN (23 31 usually) is NOT an actual PIN

2. Turn the car off
3. Use the new key (already cut to shape of course) and turn it to RUN position, just like in a normal connection procedure. Don't try to start the engine, it will not work yet.
4. Connect to the vehicle as usual
5. Find "Ignition Key programming - BETA" or similarly named adaptation (use the search)
6. Select the correct WCM if applicable (the same as you used to read the PIN)
7. Run the adaptation and follow the instructions

If needed, consult `troubleshooting`_ section.

How it works
=================================

What JScan does?
----------------

JScan instructs the vehicle to bind the key with the immobilizer, allowing the key to start the vehicle. To complete the procedure a vehicle PIN is required:
	- in some vehicles the PIN can be retrieved with JScan
	- in others, it can be obtained from a dealership
	- most recent (MY 2018+) are not supported due to more complex security measures (and not even a code from the dealer will help)

What JScan doesn't do?
----------------------

JScan (nor any other device / software, even the professional ones) does not bind the key on its own - it only instructs the vehicle to do it.

JScan doesn't handle the fob buttons binding process. This happens automatically between the key and the vehicle ECU.

Jscan doesn't remove previously programmed keys - there is no known way to un-bind a key. It is important to consider that when adding new keys because most vehicles have a maximum count of keys that can be added.



.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting
.. _troubleshooting: https://jscan-docs.readthedocs.io/en/latest/general/troubleshooting.html
