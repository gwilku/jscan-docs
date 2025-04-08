####################
Axle Ratio change
####################

Changing the axle ratio works in a similar way on the vehicles that support it. What is important though are the steps AFTER making the changes.

.. attention:: **Make sure your engine is NOT RUNNING**

1. `Connect`_ to your vehicle
2. Wait for the VIN to be discovered
3. Open Adaptation
4. Open Tire & Axle settings.
5. Open Axle Ratio
6. Read the help (?) if present
7. Choose a value from the drop-down list. 

	.. note:: If you pick a value that doesn't match the actual physical gears, you will be getting all sorts of gear ratio errors once you start driving.
8. Tap Go

Once done, follow the steps indicated in the help section. For example, on the JK Wrangler (automatic transmission) this means:

1. **Do not drive yet**
2. Run the Initialize EGS adaptation
3. Follow the instructions on screen

When procedure is completed turn ignition to off. Leave the car, close & lock the door. Take a 5 min break.

After 5 min, start the car and do a test drive and check if all is fine. If you have any problems, check `troubleshooting`_ section.


Notes:
======

If you've installed Dana 60 axles on a model equiped with Dana 30 or 44 model, you will need to consider the difference in ABS tone ring tooth count (60 vs 52).

There are two ways of handling this:

Easier:
-------

You can set the axle ratio & tire size to a value multiplied by 0.86666~ (60/52) to cheat the system. For Example:

Gear Ratio Calculations:

5.38 x 0.8666666666666667 = 4.66
5.13 x 0.8666666666666667 = 4.45
4.88 x 0.8666666666666667 = 4.23

Tire Size Calculations:

42 x 0.8666666666666667 = 36.40
40 x 0.8666666666666667 = 34.67
37 x 0.8666666666666667 = 32.07

More complex:
-------------

This method is not 100% confirmed, but theoretically is the proper way to address the tone ring tooth count difference.

After changing the axle ratio and initialising EGS:

1. Go to JScan settings > App & Adapter settings
2. Enable 'Show advanced adaptations'
3. Restart the app
4. Connect to the vehicle
5. Go to Adaptation > Tire & Axle settings
6. You will see two new adaptations:

- ABS Front Tone Wheel Teeth Count
- ABS Rear Tone Wheel Teet Count

Set both of them to 60

7. Go to Adaptation > Vehicle Maintenance
8. Run ABS Initialization

If successful, turn the ignition to off, lock the door for 5 minutes. Take a break. 
After 5 minutes, go for a test drive.



.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting
.. _troubleshooting: https://jscan-docs.readthedocs.io/en/latest/general/troubleshooting.html
