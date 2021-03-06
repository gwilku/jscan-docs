#########
Dodge RAM
#########

.. note:: This is *NOT A FULL LIST* of features available for modification, rather a colletion of more complex, vehicle-specific settings. For a complete list of features go to the JScan app and use demo mode connection.

Modules
=======
The modules section of the app gives access to actual control modules of the vehicle, live data provided by them and module-specific Activations.

.. note:: Activation is a "live" change that will **NOT** be stored after vehicle restart.

Dodge Ram 2015
--------------

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



Adaptations
===========
The Adaptation section allows making changes to various settings in the ECU.
.. note:: Adaptations are permanent.


Disabling TPMS
--------------

Dodge RAM: After disabling TPMS you need to re-initialize Radio Frequency Hub, which requires vehicle PIN. And this is to be tested.


See `ESS - Engine Start/Stop System`_ in Wrangler JL section