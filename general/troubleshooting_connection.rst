
.. attention:: Do NOT purchase the license as a “fix". The license has nothing to do with the communication between the devices.

.. note:: iPhones work with BT 4.0 (BLE) or newer adapters only.

First steps:
============

If you **CAN'T CONNECT** or **JScan CAN"T READ THE VIN** follow these steps:

1. Make sure the key is in RUN, not ACC position.
2. Make sure you are using a **supported adapter** (check the list of `compatible adapters`_).
3. Make sure your phone has Bluetooth or Wi-Fi enabled (depending on the adapter type).
4. Make sure you gave JScan all required permissions
5. Make sure you **choose the correct adapter** from the list

.. note:: The *Auto-connect* option is for BT 4.0 (BLE) devices only, and they should be used with the *auto-connect* only.

6. Make sure no other OBD applications are using the adapter
7. Uninstall Torque, vLinker, OBD Link native app etc. They work in the background preventing JScan from connecting (even when not used)
7. Make sure you **choose the right vehicle model**. The year ranges are there for a reason.
8. Make sure you are connecting to the right vehicle & adapter. If you have more than one around, you may be reaching a different device.
9. If youe vehicle model or year is not in the app, it's not supported. Choosing a different one will almost never work.

JScan doesn't read the VIN
==========================

If all above has been checked, but the app still can't read the VIN you may try specifying explicitly, which module you want to query for the VIN.

Go to JScan settings > App and adapter settings > scroll to the end, and change the value in Alternative VIN Source. The available options are:

- TCM
- PCM
- ABS
- RFH
- BCM
- WCM
- TIPCGW

If the connection is established, but JScan features don't work (adaptations fail, can't read data etc.) it is usually an issue with the adapter, especially if it's a cheaper one, or with another OBD app working in the background. See points 6 & 7 above.

OBD Adapter check
=================

Go to JScan settings and tap on *ELM327 Identification*.

- If every row reports TRUE (green) then the adapter is most likely fine. It means it is responding to basic OBD commands (it does not mean that it's capable of performing all adaptations though - again, check the list of supported adapters).
- If any row reports FALSE (red) then there is a communication issue:
	- All rows except the Module are testing the communication between your phone and the adapter. Any issues here usually indicate an unsupported or malfunctioning adapter. Replace the adapter.
	- The Module row is an adapter-vehicle communication test. If it's red, there are multiple possible reasons:
		* The car is not turned on (set the key to RUN, not ACC)
		* The socket connection is bad (check the pins 6 & 14 for OBD2 network connectivity)
		* The adapter is faulty (replace the adapter)
		* Other, unknown causes - get in touch with us

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


.. _compatible adapters: http://jscan.net/supported-and-not-supported-obd-adapters/