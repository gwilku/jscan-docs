#########
RAM
#########

.. note:: This is *NOT A FULL LIST* of features available for modification, rather a colletion of more complex, vehicle-specific settings. For a complete list of features go to the JScan app and use demo mode connection.


RAM 2015
==============

How to disable TPMS System

1) Disable TPMS Premium (Instrument Cluster) or/and TPMS Base

2) Go to Adaptations > Radio Frequency Hub - adaptation settings. From there:

3) Read vehicle PIN

4) Run Radio Frequency Hub Replace Procedure

5) Open !Restart All ECUs and from the drop-down choose "Instrument Cluster - Power On Restart" and tap GO.

6) Once completed, turn the car off completely

7) Close the door, wait a minute or two, open the door

8) Done: start the car, TPMS should be gone


EU Lights Conversion

1) Rear Lights Combined -> Deactivated

2) Rear Turn Lamps Output Present -> Activated 

3) Add two wires to BCM Pin 42 and 3 

4) Check turn signals either add new bulbs for turn signals or change lights do whaterver you want.


Disabling / Changing TPMS
=========================

RAM DS: After disabling TPMS you need to re-initialize Radio Frequency Hub, which requires vehicle PIN. See the steps above.

RAM DT will not allow a threshold lower than 25 PSI.

Disabling Engine Start-Stop
===========================


See `ESS`_ - Engine Start/Stop System in Wrangler JL section


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