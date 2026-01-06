#########
RAM
#########

.. note:: This is *NOT A FULL LIST* of features available for modification, rather a colletion of more complex, vehicle-specific settings. For a complete list of features go to the JScan app and use demo mode connection.

.. attention:: In RAM DS, and possibly other models, after disabling or the TPMS or changing the thresholds you need to re-initialize Radio Frequency Hub, which requires vehicle PIN. See the steps below.


Disabling the TPMS System / Changing thresholds
================================================

1) Disable TPMS Premium (Instrument Cluster) or/and TPMS Base OR set new thresholds

2) Go to Adaptations > Radio Frequency Hub - adaptation settings. From there:

3) Read vehicle PIN

4) Run Radio Frequency Hub Replace Procedure

5) Open !Restart All ECUs and from the drop-down choose "Instrument Cluster - Power On Restart" and tap GO.

6) Once completed, turn the car off completely

7) Close the door, wait a minute or two, open the door

8) Done: start the car, TPMS should be gone

.. note:: RAM DT will not allow a threshold lower than 25 PSI.


EU Lights Conversion
====================

1) Rear Lights Combined -> Deactivated

2) Rear Turn Lamps Output Present -> Activated 

3) Add two wires to BCM Pin 42 and 3 

4) Check turn signals either add new bulbs for turn signals or change lights do whaterver you want.


.. note:: In RAM DT if your lights switch doesn't work as expected, you may need to change the Country Code setting to Europe. Please note that changing this setting on other models usually triggers a "Vehicle Configuratiuon Mismatch" error, so if that's the case, revert the setting to the original value.

Disabling Engine Start-Stop
===========================

See `ESS`_ - Engine Start/Stop System in Wrangler JL section

TRX Suspension Rebound Reset & Height Sensor Calibration
========================================================	

For the Ram 1500 TRX, JScan provides two sequential service functions to recalibrate the suspension. These must be performed in the correct order

Engine off, vehicle on level groud, ignition in RUN position.

1) PCM – TRX Suspension Rebound Reset: With the vehicle lifted and all wheels off the ground (suspension fully unloaded), run this service function

2) ADCM – Height Sensor Calibration: Lower the truck back to the ground at normal ride height, then run this calibration routine. This ensures the suspension height sensors are calibrated under normal load conditions.

3) After both routines are complete, clear trouble codes on all modules, cycle ignition, and verify proper operation of the suspension system.

Make sure to perform both routines in this order and under the specified conditions to properly reset and calibrate the TRX’s suspension.

All data related to the suspension system can be found in the ADCM module.

	.. image:: ../img/trx/ram_trx_in_air.jpg
		:width: 400px

	.. image:: ../img/trx/ram_trx_adcm_dtc.jpg
		:width: 200px

	.. image:: ../img/trx/adcm_dtc_jump.jpg
		:width: 200px

Tire Size Change
================

.. note:: RAM DT 2020+ vehicles have a factory maximum tire size limit of 35", above which Park Sense will be disabled and throwing errors. There is currently no way to bypass or override it.

In newer RAM DS vehicles:
 
 - Change the tire size as usual
 - Turn the key to OFF
 - Turn the Key to RUN again (don't start the engine)
 - Connect and run ABS Static Init 

Failing to do that will result in an ABS error.




.. _troubleshooting: https://jscan-docs.readthedocs.io/en/latest/general/troubleshooting.html
.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting
.. _ESS: https://jscan-docs.readthedocs.io/en/latest/jeep/jeep.html#ess-engine-start-stop-system