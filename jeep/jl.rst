Choosing the right adapter
==========================

Jeep JL (and JT) are quite advanced in terms of electronic systems installed in the vehicle. Some of these systems don't operate on the standard CAN bus network, and to access them you will need either the Vlinker MS or vLinker MC+ OBD or Link MX+ adapter.

The affected modules are:

- HVAC (Heat, Ventilation, Air Conditioning)
- BSM (Blind Spot Module)
- some other radio features

Bypassing the Security Gateway
==============================

Chrysler’s Secure Gateway Module came out in 2018. The SGW is a module whose function is simply to keep the communication networks secure. The SGW protects the vehicle networks from being exploited by creating a firewall between two portions of the network with the most vulnerability. This means, that to make any changes, you will need a SGW bypass - usually a cable. See our `SGW Bypass`_ page for details.



Changing TPMS thresholds
========================

1. `Connect`_ to your vehicle
2. Open Adaptation
3. Open TPMS settings
4. Set TPMS thresholds in the following:

	- Light Load Inflation Pressure Front / Rear Tire: Leave at 0.
	- Max Load Inflation Pressure Front / Rear Tire: This value is used as the **minimum** pressure. Change this to your liking.

5. Close the car, let it sit for a few minutes, and then go for a test drive and reach minimum of 30mph then system should relearn the new settings.

6. If you see no change in behaviour, continue to the next step:

7. Reset the TPMS. Use **!Restart all ecus** option:

	- from the drop-down menu choose Tire Pressure Monitor - Power On Restart
	- tap GO
	- once procedure is complete, repeat step 5.



ESS - Engine Start/Stop System
==============================

.. warning:: ESS settings **will not work** on their own. A small hardware change si required and the warning light for ESS **will remain**.

To successfully disable the ESS you will need to complete **both** changes below:

Software settings:
------------------

1. Connect to your vehicle in JScan
2. Go to Adaptation > Auto Stop/Start (ESS) Settings and see the following:

	.. image:: ../img/JL_ESS.jpg

	a) Auto Start/Stop On/Off - disable this setting to stop the ECU from monitoring the Hood Ajar switch.
	
	.. note:: This will also disable Remote Start feature.

	b) Auto Start/Stop Menu Present On/Off - disable this setting to remove the ESS-related menu entries on your instrument cluster (dashboard).
	
	.. note:: If you don't want to disable ESS but want to explore any issues with the system, enable this option - it will give you quite a good overview of the system status.

3. Disconnect JScan
4. Turn the vehicle OFF

Hardware mod:
-------------

Open the hood and follow the instructions below to disengage the Hood Ajar sensor:

	a) The sensors (two of them) are basically simple switches. Located just next to the grille on the left side of the vehicle (on your right, when you stand in front and look at the hood).

	b) You need to remove only one of the sensors, but leave it plugged in to the harness

	c) On the top side of the sensor, there are two tabs in the ring that mount the sensor to the metal bracket. Press both of them to release the sensor.

	d) Pull the sensor up

	e) Gently pry the plastic tab that holds the sensor together to disconnect the top part

	f) Pull the cable along with the lower part through the metal bracket opening

	g) Reassemble the sensor and secure it below & behind the bracket in an extended position (do not squeeze it - you want to simulate the hood open state)

Tire size - Manual transmission
===============================
When changing tire size in a JL with a **manual** transmission it is necessary to follow the procedure below to avoid DTC P08A6 error.

1. Restart the PCM (Power Control Module) by either disconnecting the battery (batteries) or using JScan *!Restart all ECUs* adaptation
2. Once reset, drive the Jeep so:
	a) Vehicle speed is 40-80mph, in 6th gear
	b) Accelerator pedal position is more than 0.392 volts
	c) Flywheel torque is >75 Nm
3. Drive like this for at least 20 seconds.
4. Once the module reads all the data it will re-enable the all gear sensor performance diagnostic.


Axle ratio - Manual transmission
================================

After changing the axle ratio on a JL with a manual transmission you may need to run the PCM - clutch replacement eeprom reset procedure to prevent the vehicle from entering the limp mode.


Adding dedicated LED DRLs (also to JL Sport)
============================================

If you have a Rubicon or Sahara:

Factory fenders have dedicated DRL wires. You need to activate both the outputs for them to work correctly. Also you need to remember that factory DRL are LED.

Required adaptations to change:

Activate:
- Left Dedicated DRL Output Present
- Right Dedicated DRL Output Present
- Day Time Running Lights Present
- LED Dedicated DRL Present
- DRL Customer Setting
- Daytime Running Lights Customer Settings (radio)

Set:
- DRL Lamp Location - Dedicated
- DRL Configuration- Canada or Europe

The Sport version of JL doesn't have the DRL wiring in the fenders. The DRL output wires reach the connector to which the fender harness is plugged in, but the fender harness itself doesn't have the DRL wires, so you will need to add the required wires.


LED lights / indicators warning
===============================

The best results are achieved when doing the changes in the following order:

1. Go to Adaptation
2. Navigate to the LED settings group
3. **DISABLE** "LED xyz Present On/Off" for the type of lights you want to convert to LED if you changed it already
4. **Disable** the corresponding **diagnostics** options.
5. Run !Restart All ECUs (PowerOn Restart)
6. Cycle the ignition (turn the Jeep off, wait a few seconds, turn it on to RUN again)
7. Re-connect if necessary
8. **Enable** "LED xyz Present On/Off" for the type of lights you want to convert to LED

.. note:: By default JL is equipped in LED diagnostic options and you need to disable it first before activating LED options. LED diagnostics are only checked when you turn on LED options


Enabling auto high beam option on Jeep JL / JT
==============================================

.. note:: - this REQUIRES you have the forward facing module up center of the windshield, in the area of the inside rear view mirror. This contains the DASM. It's the radar and camera that handles ACC, Forward Collision Warning, etc.

This option may not work on early 2019 JL models - software update at the dealer may be required. 

If you do not have that black box up there, you cannot enable auto high beams.

Go to Adaptations and open group "Auto Headlamp & Auto High Beam"

-  Auto High Beam -> Activated  it will activate this option
-  Auto High Beam Module Location -> Select IRCM - this tells ecu where the module is installed
-  Auto High Beam On Threshold -> 25 km/h - this is default on some cars, on others it is 0 and in booth cases it should work.
-  Auto High Beam Off Threshold -> 20 km/h - this is default on some cars, on others it is 0 and in booth cases it should work.
-  Auto High Beam CSM Present-> Activated Radio settings screen under "Lights", adds the menu selection so you can turn it on or off


Jeep JL/JT/4XE front "Off Road" Factory Camera install with CVPM module
=======================================================================

-  Off Road Capable -> Activated
-  Off Road Camera Present -> Activated
-  Rear Camera Present -> Deactivated
-  Reversible Washer Pump Enable -> Activated
-  Connector A Pin 14 - Washer Motor Control Right -> Active
-  Rear View Camera Gridlines On/Off - Deactivated
-  Rear Camera Customer Settings Menu on Radio On/Off - Deactivated
-  Auto Launch Forward Facing Camera Off Road Plus CSM Present -> Deactivated
-  Auto Launch Off Road Plus Customer Settings Menu -> Activated
-  Forward Facing Camera Grid Lines Customer Settings Menu Enable/Disable -> Active
-  Rear CVPM Camera Dynamic Gridlines - Customer Settings Menu Enable/Disable -> Active
-  Rear CVPM Camera Static - Customer Settings Menu Enable/Disable -> Active
-  CVPM Module -> Active


Off-Road Pages Activation in Jeep Wrangler JL/JT Using JScan
=======================================================================

What You’ll Need:
Radio 8.4 other versions don't have Off-Road pages
A compatible OBD2 adapter with CAN-MS access (e.g., vLinker MC+,vLinker MS, OBDLink MX+, ).
SGW Bypass module (Security Gateway Bypass) – required for making changes and ensuring proper functionality.

Connect to Your Vehicle

In the JScan app, go to Adaptations or Body Module - Configuration.
Look for the Off-Road Pages option

Enable Off-Road Pages

Change the Off-Road Pages setting to Enabled.
Save the changes and follow any on-screen instructions.

Restart the Uconnect System (Radio Restart via JScan)

After enabling Off-Road Pages, you must perform two (2x) Uconnect (radio) restarts using the JScan app.
This restart function is only available when using an OBD2 adapter with CAN-MS access.
Navigate to Adaptations -> Vehicle Maintance in JScan and select !Restart -> find Radio and run restart twice.
Full System Reboot (if necessary)

If Off-Road Pages do not appear after the JScan restarts, try disconnecting the battery for a few minutes or performing a hard reset of Uconnect.
Verify Activation

Once the system reboots, check if the Off-Road Pages tab appears in the Uconnect menu.

Important Notes:

Jeep Wrangler JL has a built-in Security Gateway (SGW) that blocks unauthorized changes, so you must install an SGW Bypass module before making any modifications.
The SGW Bypass must remain installed for Off-Road Pages to function correctly after activation.
The JScan radio restart feature is only available with an OBD2 adapter that supports CAN-MS. Without CAN-MS access, you will need to manually restart Uconnect (by disconnecting the battery).
Some Uconnect versions may require additional coding or software updates.
Ensure you have the latest version of JScan and a compatible OBD2 adapter.
If Off-Road Pages do not appear, try re-saving the settings and performing another radio/system restart.
Now you're all set to enjoy the Off-Road Pages feature in your Jeep Wrangler JL! 🚙💨


Jeep JL LED Tail Lamp settings JScan - this is general guide, it may be slightly different for your car
=======================================================================

Basically there are 2 types of aftermarket LED lights

1) with resistor – those type of lamps will act like standard bulb lamps
2) without resistor – those type of lamps will act like factory led but without diagnostic

All changes should be done in: Body -> Configuration

1) With resistor
LED Rear Turn Lamps Present -> “Not Set”
LED Reverse Lamps Present -> “Not Set”
LED Stop Lamps Present -> “Not Set”
LED Tail Lamps Present -> “Not Set”
Left Rear Turn Lamp Diagnostic Present -> “Not Set”
Right Rear Turn Lamp Diagnostic Present -> “Not Set”

2) Without resistor:
LED Rear Turn Lamps Present -> “Set”
LED Reverse Lamps Present -> “Set”
LED Stop Lamps Present -> “Set”
LED Tail Lamps Present -> “Set”
Left Rear Turn Lamp Diagnostic Present -> “Not Set”
Right Rear Turn Lamp Diagnostic Present -> “Not Set”


When you are don with settings go to Body Module and clear all trouble codes (DTC).
Then lock the car and wait for power cycle (instrument cluster goes to sleep) sometimes it may be required 2x
Then you can start testing, it’s important to test with engine started.
You can leave OBD adapter connected all the time.
All lights are managed from Body module so all codes related to instrument cluster messages are visible there



Disable Sign and Lane assist 
=========================================

Jeep JL disable Sign and Lane assist

1) Go to Modules > Body Controller > Configuration
2) Set these to disabled:

- Lane departure warning present
- Traffic Sign Info

Activating Front Camera (CHML) on 2018+
=========================================

Adding a forward-facing trail camera to your Jeep Wrangler JL (model years 2018+) can greatly aid in off-road navigation and tight parking situations. Fortunately, all Wrangler JLs equipped with the 8.4-inch Uconnect infotainment system (Panasonic radio) have a built-in provision for an auxiliary video input, originally intended for a cargo or CHMSL camera (typically used on truck bed or third brake light cameras).
Any NTSC camera is compatible with this setup, just get one with a wide-angle lens for the best view, also check if this camera has option to mirror the image if needed.

1) Go to Modules > Body Controller > Configuration
2) Set these to active:

- CHML Camera Present
or
- Cargo Camera Present

3) Restart the Radio using JScan 2x - this is required for the settings to take effect.

Wire the Camera in to radio connectors:
- 2018/2019 - pin 24, black in 25  
- 2020+     - pin 21, black in 22  
Warning some late 2019 models have different pinouts, please check before wiring.

	.. image:: ../img/radio/chml.jpg
	:width: 200px

.. include:: ../general/dasm.rst


.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting
.. _SGW Bypass: http://jscan.net/jl-jt-security-bypass/