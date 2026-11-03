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

.. include:: ../general/bcm_pn_light_conversion.rst

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

Enable Front Fog Lights with High Beam 
==========================================================

This procedure allows the front fog lights to remain ON when high beam headlights
are activated in Jeep Wrangler vehicles.

From factory configuration, fog lights automatically turn OFF when high beams are enabled.
Using JScan, this behavior can be modified through the Body Module (BCM).

Procedure
---------

1. Turn ignition to **RUN** (engine OFF).
2. Connect JScan to the vehicle.
3. Open the **Body Module (BCM)** module.
4. Navigate to **Configuration**.
5. Search for the setting related to fog light behavior with high beams  
   (e.g. *Fron Fog Lamp Dropout Enable* or similar wording).
6. Change the setting to **Disabled** (or equivalent option allowing fog lights to stay ON).
7. Confirm and write the configuration to the vehicle.

After Completion
----------------

- Turn ignition OFF.
- Wait at least 30 seconds.
- Turn ignition back to RUN.
- Verify that fog lights remain ON when high beams are activated.
- Clear any stored Diagnostic Trouble Codes (DTCs) if necessary.

Important Notes
---------------

- This modification changes factory lighting behavior.
- Ensure compliance with local road regulations before enabling this feature.
- Some regional configurations may use slightly different naming for the setting.


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


Jeep JL LED Tail Lamp settings JScan 
=======================================================================

.. note:: This is general guide, it may be slightly different for your car

Basically there are 2 types of aftermarket LED lights

1) with resistor – those type of lamps will act like standard bulb lamps
2) without resistor – those type of lamps will act like factory led but without diagnostic

All changes should be done in: Body -> Configuration

1) With resistor
	- LED Rear Turn Lamps Present -> “Not Set”
	- LED Reverse Lamps Present -> “Not Set”
	- LED Stop Lamps Present -> “Not Set”
	- LED Tail Lamps Present -> “Not Set”
	- Left Rear Turn Lamp Diagnostic Present -> “Not Set”
	- Right Rear Turn Lamp Diagnostic Present -> “Not Set”

2) Without resistor:
	- LED Rear Turn Lamps Present -> “Set”
	- LED Reverse Lamps Present -> “Set”
	- LED Stop Lamps Present -> “Set”
	- LED Tail Lamps Present -> “Set”
	- Left Rear Turn Lamp Diagnostic Present -> “Not Set”
	- Right Rear Turn Lamp Diagnostic Present -> “Not Set”


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

Transfer case swap on JL or JT
=========================================

T241 (MP1622 / MP1622C)
-----------------------
- Classic mechanical part-time transfer case (Command-Trac / Rock-Trac)
- Rigid front–rear connection (no center differential, no clutch)
- Modes: 2H / 4H / N / 4L, no AUTO mode
- 4WD use only on loose/slippery surfaces (snow, mud, off-road)
- Available with low range ratio: 2.72:1 or 4:1 (Rock-Trac)

T246 (MP3022 / MP3022C)
-----------------------
- Active on-demand 4WD system (Selec-Trac) with multi-plate clutch
- Automatic torque distribution (4H Auto) with part-time lock capability
- Modes: 2H / 4H Auto / 4H Part-Time / N / 4L
- Suitable for all surfaces, including dry pavement
- Available with low range ratio: 2.72:1 or 4:1 (Rock-Trac)

1) Go to Modules > Body Controller > Configuration
2) Select correct transfer case type:
	- T241 - (MP1622/MP1622C)
	- T246 - (MP3022/MP3022C)

Important Notes
---------------
This is only part of the transfer case swap process. You will also need to perform the necessary mechanical modifications, including:
- Installing the new transfer case
- Replacing Drive Train Contol Module (DTCM) located on ther back of the car
- Replacing the transfer shift leaver and add missing wires to the harness


Disable Electric Power Steering (EPS) – Jeep Wrangler JL / JT
==============================================================

This procedure allows deactivation of the factory Electric Power Steering (EPS)
system in Jeep Wrangler JL and Jeep Gladiator JT vehicles.

This is typically required when:

- Converting from factory Electric Power Steering to a hydraulic steering system
  (e.g. PSC hydraulic pump installation)
- Performing engine swaps (e.g. 5.7L HEMI or 6.4L HEMI conversions)
- Installing aftermarket steering systems that do not use the OEM EPS module

Procedure
---------

1. Turn ignition to **RUN** (engine OFF).
2. Connect JScan to the vehicle.
3. Open the **Body** module.
4. Navigate to **Configuration**.
5. Search for **EPS (Electric Power Steering)**.
6. Set value to **Not Set**.
7. Confirm and write the configuration to the vehicle.

After Completion
----------------

- Turn ignition OFF.
- Wait at least 30 seconds.
- Turn ignition back to RUN.
- Clear any stored Diagnostic Trouble Codes (DTCs).
- Verify that no EPS-related warnings remain active.

Important Notes
---------------

- Setting EPS to **Not Set** disables factory electric steering assist.
- A properly installed hydraulic steering system must be present before driving.
- Intended for custom/off-road applications only.
- Always ensure compliance with local regulations before modifying steering systems.

2025 tire size change FFCM calibration issue
============================================

After changing the tire size on a late 2025 you may run into an FFCM calibration issue.
This is a module software bug, and has been recognised by Jeep.

Please see this `Technical Service Bulletin`_ (TSB) and contact the dealer. 


Activating Front Camera (CHML) on 2018+
=========================================

Adding a forward-facing trail camera to your Jeep Wrangler JL (model years 2018+) can greatly aid in off-road navigation and tight parking situations. Fortunately, all Wrangler JLs equipped with the 8.4-inch Uconnect infotainment system (Panasonic radio) have a built-in provision for an auxiliary video input, originally intended for a cargo or CHMSL camera (typically used on truck bed or third brake light cameras).
Any NTSC camera is compatible with this setup, just get one with a wide-angle lens for the best view, also check if this camera has option to mirror the image if needed.

1) Go to Modules > Body Controller > Configuration
2) Set these to active:	
	- CHML Camera Present or Cargo Camera Present
3) Restart the Radio using JScan 2x - this is required for the settings to take effect.

Wire the Camera in to radio connectors:
	- 2018/2019 - pin 24, black in 25  
	- 2020+     - pin 21, black in 22

.. warning:: Some late 2019 models have different pinouts, please check before wiring.

	.. image:: ../img/radio/chml.jpg
		:width: 200px

DTCM Compatibility Guide
============================================

Overview
--------

The Drivetrain Control Module (DTCM) controls and monitors
various drivetrain functions in the Jeep Wrangler JL,
depending on the vehicle configuration.

Different DTCM part numbers are used depending on the
vehicle's drivetrain equipment.

When replacing or retrofitting a DTCM, selecting a compatible
module is important to ensure proper operation of the
transfer case, differential lockers, and 4Auto system.

A DTCM from a different Wrangler JL trim level may be
compatible, provided that the required drivetrain features
are supported.


Transfer Case Gear Ratios
-------------------------

Jeep Wrangler JL vehicles are equipped with different
transfer cases, including:

* Rock-Trac with a 4.0:1 low-range ratio.
* Command-Trac with a 2.72:1 low-range ratio.
* Selec-Trac with a 2.72:1 low-range ratio and 4Auto.

**Important:**

DTCM modules used in Rubicon models can support both
4.0:1 and 2.72:1 transfer case ratios.

Likewise, compatible DTCM modules from other Wrangler JL
versions can be used with either transfer case ratio.

The transfer case ratio alone does not determine DTCM
compatibility.

The most important factors are:

* 4Auto system availability.
* Electronic differential locker support.
* Compatible DTCM hardware and software configuration.

The selected module must match the vehicle's 4Auto and
differential locker configuration.


DTCM Compatibility Rules
------------------------

DTCM modules can be divided into four main configurations.

+-------------------+-------------------+-------------------------+
| Differential      | 4Auto             | Typical Application     |
| Lockers           |                   |                         |
+===================+===================+=========================+
| No                | No                | Sport, Sport S, Willys  |
+-------------------+-------------------+-------------------------+
| Yes               | No                | Rubicon                 |
+-------------------+-------------------+-------------------------+
| No                | Yes               | Sahara with Selec-Trac  |
+-------------------+-------------------+-------------------------+
| Yes               | Yes               | Rubicon with 4Auto      |
+-------------------+-------------------+-------------------------+

**Important:**

The DTCM part number must be selected according to the
vehicle's actual drivetrain equipment, not simply its
trim level.

For example, a Rubicon DTCM without 4Auto should not be
considered interchangeable with a Rubicon DTCM equipped
with 4Auto without verifying compatibility.

Similarly, a DTCM without differential locker support
should not be selected for a vehicle requiring electronic
differential locker control.


How to Identify the Correct DTCM
--------------------------------

Before selecting a replacement DTCM, determine the
following vehicle information:

1. Model year.
2. Transfer case type.
3. Presence of the 4Auto system.
4. Presence of electronic differential lockers.
5. Original DTCM part number.

The original DTCM part number can be obtained using
JScan or read directly from the module label.


Finding the DTCM Part Number Using JScan
----------------------------------------

1. Connect JScan to the vehicle.
2. Select the correct Jeep Wrangler JL model.
3. Establish a connection with the vehicle.
4. Open the ECU list.
5. Select the Drivetrain Control Module (DTCM).
6. Open ECU identification information.
7. Locate and record the module part number.

Depending on the module, additional hardware and software
identification information may also be available.

The part number can then be compared with the
compatibility table below.


DTCM Part Number Reference
--------------------------

The following table provides reference information for
DTCM modules used in Jeep Wrangler JL vehicles.

Model-year ranges and trim applications are approximate.
Individual part numbers and supersessions should be
verified using the vehicle VIN and Mopar parts catalog.

+--------------+---------+--------+-------------+-----------------------+
| Part Number  | Lockers | 4Auto  | Model Years | Typical Models        |
+==============+=========+========+=============+=======================+
| 68409903AA   | No      | No     | 2018-2019   | Sport, Sahara         |
+--------------+---------+--------+-------------+-----------------------+
| 68409904AA   | Yes     | No     | 2018-2019   | Rubicon               |
+--------------+---------+--------+-------------+-----------------------+
| 68409905AA   | No      | Yes    | 2018-2019   | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68409906AA   | Yes     | Yes    | 2018-2019   | Rubicon 4Auto         |
+--------------+---------+--------+-------------+-----------------------+
| 68416517AA   | No      | No     | 2019-2020   | Sport, Sahara         |
+--------------+---------+--------+-------------+-----------------------+
| 68416518AA   | Yes     | No     | 2019-2020   | Rubicon               |
+--------------+---------+--------+-------------+-----------------------+
| 68416519AA   | No      | Yes    | 2019-2020   | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68416520AA   | Yes     | Yes    | 2019-2020   | Rubicon 4Auto         |
+--------------+---------+--------+-------------+-----------------------+
| 68443547AD   | No      | No     | 2020-2022   | Sport, Willys, Sahara |
+--------------+---------+--------+-------------+-----------------------+
| 68443547AE   | No      | No     | 2020-2022   | Sport, Willys, Sahara |
+--------------+---------+--------+-------------+-----------------------+
| 68443548AD   | No      | Yes    | 2020-2022   | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68443548AE   | No      | Yes    | 2020-2022   | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68483373AC   | Yes     | No     | 2021        | Rubicon               |
+--------------+---------+--------+-------------+-----------------------+
| 68483374AC   | No      | No     | 2021        | Sport, Willys, Sahara |
+--------------+---------+--------+-------------+-----------------------+
| 68483375AC   | No      | Yes    | 2021        | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68547688AB   | No      | No     | 2021-2022   | Sport, Willys, Sahara |
+--------------+---------+--------+-------------+-----------------------+
| 68547689AB   | No      | Yes    | 2021-2023   | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68547690AA   | Yes     | No     | 2022        | Rubicon               |
+--------------+---------+--------+-------------+-----------------------+
| 68547691AA   | No      | No     | 2022        | Sport, Willys, Sahara |
+--------------+---------+--------+-------------+-----------------------+
| 68547692AA   | Yes     | Yes    | 2022        | Rubicon 4Auto         |
+--------------+---------+--------+-------------+-----------------------+
| 68547693AA   | Yes     | Yes    | 2021        | Rubicon 4Auto         |
+--------------+---------+--------+-------------+-----------------------+
| 68547694AB   | Yes     | Yes    | 2021-2022   | Rubicon 392           |
+--------------+---------+--------+-------------+-----------------------+
| 68547694AC   | Yes     | Yes    | 2021-2022   | Rubicon 392           |
+--------------+---------+--------+-------------+-----------------------+
| 68534758AE   | No      | No     | 2024-2025   | Sport, Willys, Sahara |
+--------------+---------+--------+-------------+-----------------------+
| 68534758AF   | No      | No     | 2025-2026   | Sport, Willys, Sahara |
+--------------+---------+--------+-------------+-----------------------+
| 68534759AE   | Yes     | No     | 2024-2025   | Rubicon, Rubicon X    |
+--------------+---------+--------+-------------+-----------------------+
| 68534759AF   | Yes     | No     | 2025-2026   | Rubicon, Rubicon X    |
+--------------+---------+--------+-------------+-----------------------+
| 68534760AE   | No      | Yes    | 2024-2025   | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68534760AF   | No      | Yes    | 2025-2026   | Sahara Selec-Trac     |
+--------------+---------+--------+-------------+-----------------------+
| 68534761AE   | Yes     | Yes    | 2024-2025   | Rubicon 4Auto         |
+--------------+---------+--------+-------------+-----------------------+
| 68534761AF   | Yes     | Yes    | 2025-2026   | Rubicon 4Auto         |
+--------------+---------+--------+-------------+-----------------------+

.. warning::

   This table is a preliminary reference, not an exhaustive
   factory compatibility list.

   Some part-number assignments, model-year ranges, and
   trim applications have not been independently verified.

   Do not use this table as the sole basis for purchasing
   or installing a replacement DTCM.


Replacement Part Numbers
------------------------

Some DTCM part numbers have been replaced by newer
revisions or superseding part numbers.

+------------------+------------------+
| Original PN      | Replaced By      |
+==================+==================+
| 68409903AA       | 68416517AA       |
+------------------+------------------+
| 68409904AA       | 68416518AA       |
+------------------+------------------+
| 68409905AA       | 68416519AA       |
+------------------+------------------+
| 68443547AD       | 68547688AB       |
+------------------+------------------+
| 68443547AE       | 68547688AB       |
+------------------+------------------+
| 68443548AD       | 68547689AB       |
+------------------+------------------+
| 68443548AE       | 68547689AB       |
+------------------+------------------+
| 68547694AB       | 68547694AC       |
+------------------+------------------+
| 68534758AE       | 68534758AF       |
+------------------+------------------+
| 68534759AE       | 68534759AF       |
+------------------+------------------+

.. note::

   A newer part number does not automatically guarantee
   compatibility with every vehicle using an older module.

   Always verify the replacement using the vehicle VIN,
   original module part number, and drivetrain configuration.


Front Axle Disconnect (FAD)
---------------------------

The Front Axle Disconnect (FAD) system is used on many
Jeep Wrangler JL configurations.

Depending on the vehicle, the DTCM may control and
monitor the FAD actuator.

However, the presence of FAD hardware in the vehicle
must not be confused with the DTCM's ability to support
FAD functionality.

For example, the Wrangler Rubicon 392 uses a different
front axle configuration without the conventional
FAD actuator.

This does not necessarily mean that its DTCM hardware
cannot support FAD.

When selecting a DTCM for a vehicle with FAD, verify
the module's hardware, software, and configuration
compatibility.


Important Notes
---------------

* A Rubicon DTCM can support transfer cases with both
  4.0:1 and 2.72:1 low-range ratios, provided the
  specific module and calibration are compatible.

* The transfer case gear ratio alone is not sufficient
  to determine DTCM compatibility.

* The presence or absence of 4Auto must match the
  selected DTCM configuration.

* Electronic differential locker support must match
  the vehicle's equipment.

* DTCM modules from different trim levels may be
  interchangeable when their hardware and software
  capabilities are compatible.

* FAD support should be verified separately, especially
  when using modules from Rubicon 392 vehicles.

* Part-number supersessions should be checked against
  the official Mopar catalog.


Disclaimer
----------

Incorrect DTCM selection or configuration may result in
transfer case malfunction, differential locker errors,
FAD-related diagnostic trouble codes, or unavailable
drivetrain functions.

Always verify module compatibility before installation.
```



.. include:: /general/dasm.rst

.. include:: /general/power_inverter_eu_conversion.rst


.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting
.. _SGW Bypass: http://jscan.net/jl-jt-security-bypass/
.. _Technical Service Bulletin: https://static.oemdtc.com/NHTSA-PDFs/MC-11024053-0001.pdf