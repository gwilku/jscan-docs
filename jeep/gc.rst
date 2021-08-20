Modules
=======
The modules section of the app gives access to actual control modules of the vehicle, live data provided by them and module-specific Activations.

.. note:: Activation is a "live" change that will **NOT** be stored after vehicle restart.



Adaptations
===========
The Adaptation section allows making changes to various settings in the ECU.
.. note:: Adaptations are permanent.


Tire Size
---------
.. note:: In models equipped with the advanced Park Sense module (not the basic, 4-sensor one) setting a bigger tire size **will cause Park Sense and ABS errors** and there is currently no known solution.

Generally, follow the default `Tire Size`_ procedure, and then:

	- if everything works fine after you restart the car, you're good to go
	- if you are getting an ABS error:
		- Run **ABS Initialization** adaptation
		- Run Advanced Scan and clear the error codes
		- Cycle the ignition (shut the car down, wait a moment, start it again)


Tire Size
---------
ABS Initialize


.. _Tire Size: https://jscan-docs.readthedocs.io/en/latest/general/tiresize.html