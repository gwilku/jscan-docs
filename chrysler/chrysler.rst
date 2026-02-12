############
Chrysler
############


Chrysler Pacifica
=================


Client story
------------

Since I imported a Chrysler Pacifica, I had issues with the adaptive cruise control. Tried to calibrate it 4 times (2x with JScan, 2x with other tools).

If it didn't work 4 times, it means the radar is to be replaced, so I bought a new one and installed it immediately. The next day I calibrated it with Jscan without an issue - instant smile on my face


Radar calibration
-----------------

First and foremost, you need to properly align the radar horizontally and vertically. The best solution is a dedicated tool for that.

Once the radar is levelled:

1. Put the key in RUN and connect with JScan as usual.
2. Go to *Adaptations*, tap the search icon and type "ACC".
3. Select "ACC - Sensor Calibration - BETA".
4. Follow the instructions and confirm the levelling of the radar.

.. note:: The app will hint which srew should be adjusted and how much, to set the radar perfectly. The calibration will only succeed if the deviations i below 2%.

5. After confirming the manual levelling, turn the ignition OFF, and then start the engine (don't disconnect JScan).
6. Start the calibration / learning by pressing "GO".
7. A progress indicator will appear. All items need an *OK* status, otherwise the calibration will not begin.
8. Go on a straight road with typical traffic where you can reach a speed of at least 40 km/h.
9. The whole calibration cycle may take between 5 and 15 minutes.
10. Once complete, the progress will show 100%.
11. Stop the vehicle in a safe place and tap "GO".
12. The app will hint to turn the engine off - do it.

The radar is now calibrated, and you can use the Adaptive Cruise Control (refer to your user manual). Of course test teh proper operation of the ACC: activate it, set a distance to preceeding vehicle, and verify that your car actually adjusts the speed to keep the distance.


Rear fog lamps (EU conversion) issue
------------------------------------

For hybrid cars activate rear fog lamps the same procedure as for non-hybrid, through corresponding settings.

Unfortunately in the hybrid model, it is not activating the rear fog lamp symbol on the dash. The led is in the dash. To activate it you need to change the country of delivery (Country Code) to EU. But after the change you will lose some functions: front radar, parking sensors and etc.. 

Re-calibrating the radar should be possible, but it not confirmed.



Activating the rear fog light in Chrysler Town & Country / Dodge Grand Caravan
=====================================================================================

The TIPM (Totally Integrated Power Module), which is used in the Town & Country, Dodge Grand Caravan, and Lancia Voyager is located to the right of the battery. To access the cables, remove the top cover, then unscrew the screw with a 13mm wrench and unclip the box by pulling it upwards. To install a rear fog light, you need to disconnect two wires from the C4 connector (looking from the pins, it's gray). Then, connect them together and plug them into the C7 connector, replacing PIN 6. 

	.. note:: The pin in the C7 connector is different from the one in the C4 connector – you'll need to buy one first.

You'll need to remove it with a pick and push through the plastic plug that replaces pin 6. The C7 connector is red, looking from the pins.

Next, for the T&C connectors in the rear light connectors that exit the car's body, you'll need to swap pins 3 and 5.

You'll need a multimeter in the DGC, because if I remember correctly, you had to swap three wires. A multimeter is handy, and you'll definitely be able to do it! Of course, my memory may be faulty – looking at the connector description (http://connectors.dcctools.com/details.htm?id=79157), it's identical to the one in the TC (http://connectors.dcctools.com/details.htm?id=147832).

    .. attention:: The rear light has 5 pins. The connector in the car has 6 pins – we need the pin for the light.

Then, after completing these steps, `Connect`_ to the vehicle as usual.

Go to the Adaptations section, go to "Lights Conversion US <-> Euro" and in the option:

1. Rear LED Stop and Tail Lamps Present Chrysler / Lancia mode On/Off, select Active. 
2. Rear Lighting Combined On/Off, select Deactivate.
3. Rear Fog Lamps Present On/Off, select Activate.

This activates the fog lights from the original button, using four clicks: the first turns on the front, the second turns on the rear, the third turns off the rear, and the fourth turns off the front.

TPMS
====

In a T&C or DGC, if it has a large display (EVIC) and the Basic version of TPMS is enabled, you can enable the Premium version of TPMS – it will then display the tire pressure separately on the display.

Remote Start
============

If the T&C or DGC doesn't have remote start, you can add this option – it costs 10 cents.

A 1k ohm resistor is required. You need to find the floating, separately attached, round 2-pin plug under the TIPM box. Then cut the wires and solder a resistor in their place.

Go to the Adaptations section, and use the search to find the following options:

1. Ignition Key Programming, select PIN reading by selecting WCM 6.
2. In the "Reconfig Input 2 - Hood Ajar Input" option, change it to "Hood Ajar." 
3. In "Remote Start Present," select "Active."
4. Run "WCM - Reset the WIN Configuration" (that's when the PIN is required).



.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting