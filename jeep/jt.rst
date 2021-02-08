ESS - Engine Start/Stop System
------------------------------

See `ESS - Engine Start/Stop System`_ in Wrangler JL section.

Changing TPMS thresholds
------------------------

1. `Connect`_ to your vehicle
2. Open Adaptation
3. Open TPMS settings
4. Set TPMS thresholds in the following:

	- Light Load Inflation Pressure Front / Rear Tire: This value is used as the **minimum** pressure when the **vehicle is not loaded**. Possible range is **25-80psi**.
	- Max Load Inflation Pressure Front / Rear Tire: This value is used as the **minimum** pressure when the **vehicle is fully loaded**. Do not change if not necessary, minimum value is 10psi.

5. Reset the TPMS. Use **!Restart all ecus** option.