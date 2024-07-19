#######################
Modifying your vehicle
#######################

Overview
========

There are two main ways you can modify the vehicle settings: the Adaptation section and the Modules section.

.. note:: These changes are applied to the vehicle configuration. They will persist after cycling the ignition and you can safely disconnect the OBD adapter when done (recommended).


Adaptations
===========

The Adaptation section allows making changes to various settings in the vehicle modules and run service procedures. Please be aware that:

- JScan doesn't interact with the vehicle's software directly. You need a compatible adapter, capable of handling the commands and messages exchanged between the app and the vehicle.
- Certain adaptations and procedures are available on certain typees of modules and may not work on your vehicle.
- Adaptation list is pre-built, meaning it doesn't necessarily reflect every single setting available. Check Module Configuration below for details.



Generally, the steps are as following:

1. Find JScan in your app store
2. Install JScan
3. Purchase a license (from within the app)
4. `Connect`_ to your vehicle
5. Go to Adaptation section
6. Find the setting you want to change
7. Choose a new value and tap the "GO" button.
8. Check the result - it's reasonable to restart the vehicle before you do.

.. note:: Some settings (usually safety related) can be changed with JScan, but have no real impact on the vehicle behaviour, since there are additional overrides or the vehicle software simply ignores them. There is nothing we can do about it.

Trace & Restore
===============

You can use the Trace & Restore section in JScan settings to check the history of changes and/or revert to the original state (the configuration from when you first connected with JScan).

The Trace tab shows a list of changes since the last app installation (it gets deleted upon app re-installation).

The Restore tab lets you restore all or part of the settings to the state from the first JScan connection.


Modules
=======
The modules section of the app gives access to actual control modules of the vehicle, live data provided by them and module-specific Activations.


Each module has the following sections:

- Trouble Codes: Query the module for DTCs reported
- Live Data: Read live data (PIDs) from the module. Remember 
- Activations: Live triggers / controls
- Configuration: Module's configurable options.
- Module Information: VIN(s), part# etc.

.. note:: Configuration options are read live from the module - this means if a setting you need is not on this list, it doesn't exist on your module (or has a different name).

.. note:: Activation is a "live" change that will **NOT** be stored after vehicle restart.



Trail View
===========

In some vehicles you will be able to access some "live" features, which work when JScan is connected to the vehicle. These can be used with the engine running.

.. _Connect: https://jscan-docs.readthedocs.io/en/latest/general/getting_started.html#connecting