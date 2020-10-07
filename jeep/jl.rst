Wrangler JL Modules
===================
The modules section of the app gives access to actual control modules of the vehicle, live data provided by them and module-specific Activations.

.. note:: Activation is a "live" change that will **NOT** be stored after vehicle restart.



Wrangelr JL Adaptations
=======================
The Adaptation section allows making changes to various settings in the ECU.
.. note:: Adaptations are permanent.



Tire size
*********
When changing tire size in a JL with a **manual** transmission it is necessary to follow the procedure below to avoid DTC P08A6 error.

1. Restart the PCM (Power Control Module) by either disconnecting the battery (batteries) or using JScan *!Restart all ECUs* adaptation
2. Once reset, drive the Jeep so:
	a) Vehicle speed is 40-80mph, in 6th gear
	b) Accelerator pedal position is more than 0.392 volts
	c) Flywheel torque is >75 Nm
3. Drive like this for at least 20 seconds.
4. Once the module reads all the data it will re-enable the all gear sensor performance diagnostic.

