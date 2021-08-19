Changing TPMS thresholds
------------------------

1. `Connect`_ to your vehicle
2. Open Adaptation
3. Open TPMS settings
4. Set TPMS thresholds in the following:

	- Light Load Inflation Pressure Front / Rear Tire: possible range is **25-80psi**
	- Max Load Inflation Pressure Front / Rear Tire: for vehicles that have a load sensor (Gladiator, RAM trucks). This value is used as the **minimum** pressure when the **vehicle is fully loaded**. Set to 10 on JL

5. Reset the TPMS. Use **!Restart all ecus** option:

	- from the drop-down menu choose Tire Pressure Monitor - Power On Restart
	- tap GO


ESS - Engine Start/Stop System
------------------------------

Disabling Engine Start/Stop System is possible, but requires a small hardware modification (reversible) and *will* result in a warning on the dashboard.

.. attention:: This feature is still being tested and **may or may not work** in your vehicle.

1. Connect to your vehicle in JScan
2. Go to Adaptation > Auto Stop/Start (ESS) Settings and see the following:

	.. image:: ../img/JL_ESS.jpg

	a) Auto Start/Stop On/Off - disable this setting to stop the ECU from monitoring the Hood Ajar switch.
	
	.. note:: This will also disable Remote Start feature.

	b) Auto Start/Stop Menu Present On/Off - disable this setting to remove the ESS-related menu entries on your instrument cluster (dashboard).
	
	.. note:: If you don't want to disable ESS but want to explore any issues with the system, enable this option - it will give you quite a good overview of the system status.

3. Disconnect JScan
4. Turn the vehicle OFF
5. Open the hood and follow the instructions below to disengage the Hood Ajar sensor:

	a) The sensors (two of them) are basically simple switches. Located just next to the grille on the left side of the vehicle (on your right, when you stand in front and look at the hood).

	b) You need to remove only one of the sensors, but leave it plugged in to the harness

	c) On the top side of the sensor, there are two tabs in the ring that mount the sensor to the metal bracket. Press both of them to release the sensor.

	d) Pull the sensor up

	e) Gently pry the plastic tab that holds the sensor together to disconnect the top part

	f) Pull the cable along with the lower part through the metal bracket opening

	g) Reassemble the sensor and secure it below & behind the bracket in an extended position (do not squeeze it - you want to simulate the hood open state)

Tire size - Manual transmission
-------------------------------
When changing tire size in a JL with a **manual** transmission it is necessary to follow the procedure below to avoid DTC P08A6 error.

1. Restart the PCM (Power Control Module) by either disconnecting the battery (batteries) or using JScan *!Restart all ECUs* adaptation
2. Once reset, drive the Jeep so:
	a) Vehicle speed is 40-80mph, in 6th gear
	b) Accelerator pedal position is more than 0.392 volts
	c) Flywheel torque is >75 Nm
3. Drive like this for at least 20 seconds.
4. Once the module reads all the data it will re-enable the all gear sensor performance diagnostic.



LED lights / indicators warning
-------------------------------

When original traditional lights / indicators are replaced with LEDs, even if you set the corresponding settings to let the ECU know that LEDs are present, it is possible to get a dashboard error about malfunctioning light / indicator.

If you are certain the lights / indicators work properly and want to remove the error from your dashboard:

1. Go to Adaptation
2. Tap search (a magnifying glass in a green circle)
3. Type "diagnostics"
4. Disable the corresponding "diagnostics present" setting.

This will tell the ECU not to monitor the state of the sepcified lamp or indicator.

.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting