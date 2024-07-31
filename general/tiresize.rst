####################
Tire Size change
####################

Changing the tire size works in a similar way in all vehicles. Please check the model-specific docs below and/or use the demo mode (demo adapter conenction) in JScan to check if the tire size adaptations is present at all for your model.

.. attention:: **Make sure your engine is NOT RUNNING**

1. `Connect`_ to your vehicle
2. Open Adaptation
3. Open Tire & Axle settings.
4. Set Tire Size:
	
	- Choose a value from the drop-down list. It represents a tire *diameter* in inches.

	.. note:: If you pick a value that matches your tire size exaclty, your speedometer will be showing a higher reading than your GPS. That's normal - your factory wheels with factory settings worked the same. Blame the law-makers (At least in the EU). We recommend setting a value that is about 0.5 inch smaller than your actual tire size.

	- If you enabled it in App & Adapter settings, you will have manual input availabe. This however is wheel **circumference** in mm. Not recommended.
	- With manual input enabled you migth get an error when trying to set a value from a drop-down. In that case, disable manual input.

5. **Disconnect, close the car, let it sit for a few minutes.** No ECU reset required.

Notes:
======

Some vehicles (especially the more "civilian" ones) have a max tire size value they can handle. You can set a higher one, but the ABS module will throw a warning on your dash. Decrease the tire size.

If you have any errors after setting the tire size (including because of the issue above):

1. `Connect`_ to your vehicle
2. Run Advanced Scan
3. Clear the codes
4. Fix the tire size setting
5. Restart the vehicle and see if the problem is fixed
6. If not, go to Adaptations, use search to find "ABS Static Init" (preferred) or other ABS Initialization procedure and run it.
7. Clear the error codes again
8. Restart your vehicle

If the steps above didn't solve the problem, then most likely your vehicle is not designed to accept any other value than factory. Go to JScan settings > Trace & Restore Adaptations to either check the history of changes or revert all settings to factory.

.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting
.. _Tire Size: https://jscan-docs.readthedocs.io/en/latest/general/tiresize.html
