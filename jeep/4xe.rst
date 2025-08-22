
.. warning:: Make sure you connect using **JL 4XE, not a regular JL**. Using regular JL procedures will cause errors! 


Tire size
===============================

When changing tire size in a JL 4xe, you need to run ABS Initialization procedure. ABS Static Init (Hybrid) should be used.

Follow these steps:

1) Set ignition to "RUN" and make sure "READY" info is not visible on Instrument Cluster, connect as usual (with the SGW bypass cable).
2) Go to Tire Size adaptation and chose desired tire size.
3) Hit "GO" and wait till adaptation is complete.
4) When adaptation says completed **don't start the car**.
5) Run the **ABS Static Initialize (Hybrid)** procedure.
6) When done, set ignition to "OFF", then open and close driver door.
7) Wait till instrument cluster shuts down.
8) Start the car.

Tire Size Error FIX
======================

If you connected with a JL or ignored the instructions above, follow these steps:

1) Start JScan App
2) Set ignition to "RUN" and make sure "READY" info is not visible on Instrument Cluster.
3) Connect
4) Run "Advanced scan" - and when it completes, clear all codes using dust bin icon. When it's done.
5) Set ignition to "OFF" and open and close driver door
6) Wait till instrument cluster shuts down.
7) Set ignition to "RUN" and make sure "READY" info is not visible on Instrument Cluster.
8) Go to Tire Size adaptation and chosse desired tire size
9) Hit "GO" and wait till adaptation is completed.
10) When adaptation will say completed. Don't start car.
11) Run procedure - ABS Static Initialize (Hybrid)
12) Set ignition to "OFF" and open and close driver door
13) Wait till instrument cluster shuts down.
14) Try to start car.
15) If all is fine you can disconnect OBD adapter.
16) If there is any problem, shut down vehicle.
17) Set ignition to "RUN" and make sure "READY" info is not visible on Instrument Cluster.
18) Run procedure - ABS Static Initialize (Hybrid)
19) Set ignition to "OFF" and open and close driver door
20) Wait till instrument cluster shuts down.
21) Try to start car.

Gear ratio - Warning
===============================
Early Jeep Wrangler 4xe models had a software limitation that prevented axle ratios above 4.50 from working correctly. This was due to ABS/traction control calibration, not mechanical issues. The manufacturer has since released an ABS software update that resolves the problem.
If issues occur after changing axle ratios with JScan, owners should visit an authorized Jeep dealer to check the ABS software version and apply the latest update if required.

.. include:: ../general/dasm.rst