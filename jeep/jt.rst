General hints for JT
====================

For ESS (and other features) please see the JL section above - JT shares a lot with the JL model.


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


Bed Power Outlet Install
==========================

See the `Bed Power Outlet installation`_ video (this is not our resource) for a full guide. JScan usage for settings is shown around 8:48 (linked)

	

.. _ESS: https://jscan-docs.readthedocs.io/en/latest/jeep/jeep.html#ess-engine-start-stop-system

.. _Bed Power Outlet installation:  https://www.youtube.com/watch?v=XATv5NzMnRk&t=528s
