Installing LED Fog Lights
=========================

JScan can't help much here, but please see this great guide on installing LED `fog lights`_ in your JK.

Sway Bar removal
================

.. note:: DO NOT access the Sway Bar module to disable it. That's not how it works.

1. Go to Adaptation section
2. Use the search and find:
	- ASBS Sway Bar On/Off
3. Disable it
4. Turn the ignition off, restart the vehicle.

In case there are still errors, run Advanced Scan and clear them.

TPMS
====

Follow the generic `TPMS instructions`_.

US -> EU Light conversion
=========================

If you imported a JK from the USA, you will need to adapt (among other things) the rear lights. In American version the stop light is also the turn signal. In Europe, these need to be separated.

1. `Connect`_ to your vehicle
2. Open Adaptation
3. Open "Lights conversion US<->EURO & LED"
4. Set "Rear Lighting Combined On/Off" to **disabled**

Now your side lamps will work as indicators only, and you need to route a wire from the third (central) stop light to each of the rear lamps to power the European stop lights as well.


Transmission gear ratio
=========================

Change this *only* if you physically changed the gears. Make sure you know the actual ratio (don't trust the labels on boxes).
	
1. `Connect`_ to your vehicle
2. Open Adaptation
3. Open "Tire & Axle Settings"
4. Change T-Case High and/or T-Case Low Ratio
5. Execute Initialize EGS

	.. note:: For WA580 - NAG1 automatic transmission only. This step is *not* required in JK 3.8 with an older transmission (it doesn't have the EGS).

6. Turn off the vehicle
7. Close & lock the door and leave the vehicle for a 15 min break
8. Go for a test drive
	
.. note:: If there are errors mentioning "incorrect gear ratio" see `Troubleshooting`_



Jeep Wrangler JK Automatic transmissions
========================================

Below you will find tech tips and procedures dedicated for each gearbox.
There were 3 automatic gearboxes in JK 42RLE (4 speed), 545RFE (5 speed), WA580/NAG1 (5 speed)

- JK 2.8 CRD 2007 - 2010      - 545RFE
- JK 2.8 CRD 2010 - 2018      - WA580/NAG1
- JK 3.8 Petrol - 2007-2011   - 42RLE
- JK 3.6 Petrol - 2011 - 2018 - WA580/NAG1

545RFE
------

The 545RFE transmission has its own transmission control unit
Procedures:

-  "Quick Learn" - Quick Learn should only be used when a transmission has been replaced or overhauled, or when the Transmission Control Module has been replaced or flashed.
-  "Clear VLP Counters" - Shift Counters
-  "Clear VLP Counters" - Tooth Counters

42RLE
-----

The 42RLE gearbox has a gearbox controller connected to the engine control unit (all in one module)
Procedures:

-  "Quick Learn" - Quick Learn should only be used when a transmission has been replaced or overhauled, or when the Transmission Control Module has been replaced or flashed.
-  "Clear VLP Counters" - Shift Counters
-  "Clear VLP Counters" - Tooth Counters

WA580/NAG1
----------

The WA580 gearbox has its own gearbox control unit (it is roughly to the right of the driver's feet)
Procedures:

-  Initialize EGS - This procedure will transfer data in to transmission module, it is required when you update Axle Ratio and recommend with significant Tire Size update (if you experience poor shifting).
-  TCM Reset Learned Adaptives - This procedure This program allows the electronic transmission system to re-calibrate itself.
-  TCM Store Learned Adaptives - This procedure This program allows the electronic transmission system to save current calibrations.

See NAG1 How-To for details.



Setting the Steering Angle
==========================

There is no such thing as an software initialization procedure for the steering angle sensor. If the wheels are straight and the steering column is assembled right, it will read 0.

General hints on handling steering angle issues:

Connect > go to modules > ABS > Live Data > (...) > search for steering angle > select > OK > PLAY

-  If your wheels are straight it should show 0
-  If it shows 180, the steering column part is upside down

If it is OK - start the engine, make a full turn left, full turn right. Switch back the key  to RUN (engine off) > Run Advanced Scan, see if you have any further errors.

If the steering angle is off by a different number than ~180 you'll have to inspect the steering system.


ABS Pump Bleed
==============

It's **PUMP** bleed, not a full brake sytem bleed. It's to be done after a regular brake bleed.

.. note:: Yes, it does bleed only one side. By design.


Changing the radiator fan trigger temperature
=============================================

This is *not* a setting that can be  configured with JScan. There are other tools, which modify the engine controller software / do tuning, that can do it, but this is beyond the scope of JScan app.


Axle Ratio change
==================

Changing the axle ratio works in a similar way on the vehicles that support it. What is important though are the steps AFTER making the changes.

.. attention:: **Make sure your engine is NOT RUNNING**

1. `Connect`_ to your vehicle
2. Wait for the VIN to be discovered
3. Open Adaptation
4. Open Tire & Axle settings.
5. Open Axle Ratio
6. Read the help (?) if present
7. Choose a value from the drop-down list. 

	.. note:: If you pick a value that doesn't match the actual physical gears, you will be getting all sorts of gear ratio errors once you start driving.
8. Tap Go

Once done, follow the steps indicated in the help section. For example, on the JK Wrangler (automatic transmission) this means:

1. **Do not drive yet**
2. Run the Initialize EGS adaptation
3. Follow the instructions on screen

When procedure is completed turn ignition to off. Leave the car, close & lock the door. Take a 5 min break.

After 5 min, start the car and do a test drive and check if all is fine. If you have any problems, check `troubleshooting`_ section.


Notes:
======

If you've installed Dana 60 axles on a model equiped with Dana 30 or 44 model, you will need to consider the difference in ABS tone ring tooth count (60 vs 52).

There are two ways of handling this:

Easier:
-------

You can set the axle ratio & tire size to a value multiplied by 0.86666~ (60/52) to cheat the system. For Example:

Gear Ratio Calculations:

5.38 x 0.8666666666666667 = 4.66
5.13 x 0.8666666666666667 = 4.45
4.88 x 0.8666666666666667 = 4.23

Tire Size Calculations:

42 x 0.8666666666666667 = 36.40
40 x 0.8666666666666667 = 34.67
37 x 0.8666666666666667 = 32.07

More complex:
-------------

This method is not 100% confirmed, but theoretically is the proper way to address the tone ring tooth count difference.

After changing the axle ratio and initialising EGS:

1. Go to JScan settings > App & Adapter settings
2. Enable 'Show advanced adaptations'
3. Restart the app
4. Connect to the vehicle
5. Go to Adaptation > Tire & Axle settings
6. You will see two new adaptations:

- ABS Front Tone Wheel Teeth Count
- ABS Rear Tone Wheel Teet Count

Set both of them to 60

7. Go to Adaptation > Vehicle Maintenance
8. Run ABS Initialization

If successful, turn the ignition to off, lock the door for 5 minutes. Take a break. 
After 5 minutes, go for a test drive.



.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting
.. _troubleshooting: https://jscan-docs.readthedocs.io/en/latest/general/troubleshooting.html
.. _fog lights: https://betterautomotivelighting.com/2017/09/21/installing-oem-led-myotek-jeep-wrangler-fog-lights-need-know/ 
.. _TPMS instructions: https://jscan-docs.readthedocs.io/en/latest/general/tpms.html