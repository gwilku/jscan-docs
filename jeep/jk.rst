Installing LED Fog Lights
=========================

JScan can't help much here, but please see this great guide on installing LED `fog lights`_ in your JK.

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

* "Quick Learn" - Quick Learn should only be used when a transmission has been replaced or overhauled, or when the Transmission Control Module has been replaced or flashed.
* "Clear VLP Counters" - Shift Counters
* "Clear VLP Counters" - Tooth Counters

42RLE
-----

The 42RLE gearbox has a gearbox controller connected to the engine control unit (all in one module)
Procedures:

* "Quick Learn" - Quick Learn should only be used when a transmission has been replaced or overhauled, or when the Transmission Control Module has been replaced or flashed.
* "Clear VLP Counters" - Shift Counters
* "Clear VLP Counters" - Tooth Counters

WA580/NAG1
----------

The WA580 gearbox has its own gearbox control unit (it is roughly to the right of the driver's feet)
Procedures:

* Initialize EGS - This procedure will transfer data in to transmission module, it is required when you update Axle Ratio and recommend with significant Tire Size update (if you experience poor shifting).
* TCM Reset Learned Adaptives - This procedure This program allows the electronic transmission system to re-calibrate itself.
* TCM Store Learned Adaptives - This procedure This program allows the electronic transmission system to save current calibrations.

See NAG1 How-To for details.



.. _fog lights: https://betterautomotivelighting.com/2017/09/21/installing-oem-led-myotek-jeep-wrangler-fog-lights-need-know/ 