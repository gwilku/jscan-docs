General hints for JT
====================

Please see the JL section above - JT shares a lot with the JL model.

Changing TPMS thresholds
========================

1. `Connect`_ to your vehicle
2. Open Adaptation
3. Open TPMS settings
4. Set TPMS thresholds in the following:

	- Light Load Inflation Pressure Front / Rear Tire: *SUPPOSEDLY* This value is used as the **minimum** pressure when the **vehicle is not loaded**. Possible range is **25-80psi**, however, there are reports that his value is set to 0 by default. If that's the case in your vehicle (see "Current value in ECU" when doing the adaptation), don't change it.
	- Max Load Inflation Pressure Front / Rear Tire: *SUPPOSEDLY* This value is used as the **minimum** pressure when the **vehicle is fully loaded**. Possible range is **25-80psi**.

5. Reset the TPMS. Use **!Restart all ecus** option:

	- from the drop-down menu choose Tire Pressure Monitor - Power On Restart
	- tap GO
	

.. _ESS: https://jscan-docs.readthedocs.io/en/latest/jeep/jeep.html#ess-engine-start-stop-system