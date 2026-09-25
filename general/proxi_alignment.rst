PROXI Alignment
===============

What is PROXI Alignment?
------------------------

PROXI Alignment is a vehicle configuration synchronization procedure used on selected
FCA / Stellantis platforms. It is **not a procedure used by every Jeep, Chrysler,
Dodge or RAM vehicle**.

On vehicles that use PROXI, the Body Control Module (BCM) stores the central vehicle
configuration. Other control modules connected to the vehicle network must have a
configuration that is consistent with the BCM. PROXI Alignment distributes and
synchronizes the required configuration data between the BCM and the modules that
participate in the PROXI / EOL configuration.

In this context, **EOL means End Of Line**. It refers to factory configuration data
used by the vehicle electronics. It does not mean "End Of Life".

In JScan, the PROXI Alignment screen is available only for vehicles and platforms
for which this procedure is supported.

Vehicles using PROXI
--------------------

PROXI is used only on selected FCA / Stellantis vehicle architectures. In JScan,
the procedure is available only when it is applicable to the selected vehicle.

Platforms known to use this type of configuration include:

* Jeep Cherokee (KL)
* Jeep Renegade (BU)
* Jeep Compass (MP)
* Chrysler 200 (UF)
* Dodge Dart (PF)

The exact availability can depend on vehicle year, module configuration and JScan
version. The authoritative check is the selected vehicle in JScan. The same vehicle
can also be selected in **Demo Mode** to check whether the PROXI Alignment procedure
is available before connecting to the vehicle.

.. note::

   Do not assume that a vehicle requires PROXI only because it is a Jeep, Chrysler,
   Dodge or RAM vehicle, or because it has configurable BCM settings. Other platforms
   can use different configuration and module synchronization methods.

When should PROXI Alignment be performed?
-----------------------------------------

PROXI Alignment should be considered when the configuration stored in the BCM and
the configuration used by one or more vehicle modules are no longer consistent.

Typical situations include:

* after changing vehicle configuration settings that require PROXI synchronization,
* after adding a module or feature that changes the vehicle configuration,
* after removing a module or feature from the vehicle configuration,
* after replacing certain electronic control modules,
* after an interrupted or unsuccessful PROXI Alignment,
* when one or more modules show an incorrect EOL / PROXI status,
* when the odometer starts flashing after a configuration change or module replacement.

It is not necessary to perform PROXI Alignment after every diagnostic operation.
Reading or clearing DTCs, viewing Live Data or running unrelated service procedures
does not by itself require PROXI Alignment.

Flashing odometer
-----------------

On vehicles that use PROXI, a **flashing odometer is one of the most common signs of
a configuration mismatch**.

This usually means that the network contains a module whose configuration does not
match the configuration expected by the BCM. It can happen, for example, after a
module replacement, retrofit, configuration change or unsuccessful alignment.

A flashing odometer should be treated as an indication that the vehicle configuration
needs to be checked. It does not automatically mean that simply running PROXI Alignment
will fix the vehicle. A module that is not responding, an incorrect vehicle
configuration, a communication problem or an incompatible replacement module must be
corrected before alignment can complete successfully.

Where to find PROXI Alignment in JScan
--------------------------------------

Connect to the vehicle and open::

   Body -> Service Procedures -> PROXI Alignment

The procedure is located in the **Body** section under **Service Procedures**.

If the PROXI Alignment procedure is not available for the selected vehicle, do not use
instructions intended for a different vehicle platform.

Understanding the PROXI Alignment screen
----------------------------------------

Before starting the alignment, JScan reads the current configuration and network state
and displays the status of the modules involved in the procedure.

The values should be interpreted together. A single ``True`` or ``False`` value is not
enough to determine the condition of a module.

Module Present
~~~~~~~~~~~~~~

``Module Present`` tells whether the module **should be present according to the
vehicle configuration**.

``True``
   The BCM / PROXI configuration defines this module as installed in the vehicle.

``False``
   The current vehicle configuration does not define this module as installed.

This value describes the **configured state**, not whether the module is actually
responding on the network.

Module Active
~~~~~~~~~~~~~

``Module Active`` tells whether JScan can currently detect the module as an active
module on the vehicle network.

``True``
   The module is physically present and responding on the vehicle network.

``False``
   The module is not currently detected or is not responding.

``Module Active`` is independent from ``Module Present``.

For example, a newly installed module can be ``Active = True`` while
``Present = False`` if the module is physically connected but has not yet been added
to the vehicle configuration.

Likewise, ``Present = True`` and ``Active = False`` means that the BCM expects the
module to exist, but the module is not currently responding.

.. note::

   ``Module Active = True`` confirms communication with the module. It does not mean
   that the module has no DTCs or that every function of the module is operating
   correctly.

Has EOL Value
~~~~~~~~~~~~~

``Has EOL Value`` indicates whether the module has an EOL / PROXI configuration value
associated with it.

``True``
   The module participates in the EOL / PROXI configuration and an EOL value is
   available for the module.

``False``
   The module does not use an EOL value in this PROXI configuration, or an EOL value
   is not available for this node.

This is primarily an informational value. ``Has EOL Value = True`` does not by itself
mean that the module is correctly aligned.

EOL OK
~~~~~~

``EOL OK`` indicates whether the module's current EOL / PROXI state is consistent with
the vehicle configuration.

``True``
   The module is correctly aligned for the currently read configuration.

``False``
   The module may require alignment, or its EOL state could not be confirmed correctly.

A module with ``EOL OK = False`` should always be evaluated together with
``Module Present``, ``Module Active`` and ``EOL Required``.

EOL Required
~~~~~~~~~~~~

``EOL Required`` indicates whether EOL / PROXI verification and synchronization is
required for this module.

``True``
   This module is expected to participate in the PROXI alignment.

``False``
   This module does not require EOL synchronization as part of this procedure.

Cable Adapter
~~~~~~~~~~~~~

The message shown at the bottom of each module indicates whether access to that module
requires a different CAN network connection.

For example::

   Cable Adapter not required

means that JScan can access the module using the currently selected connection without
an additional coloured adapter cable.

For vehicles where a module is located on another CAN network, JScan can instruct the
user to use the required cable or a compatible multiplexing adapter.

Typical status combinations
---------------------------

.. list-table::
   :header-rows: 1
   :widths: 18 18 64

   * - Module Present
     - Module Active
     - Meaning
   * - True
     - True
     - Normal situation. The module is configured as installed and is responding.
   * - True
     - False
     - The vehicle expects the module, but it is not responding. Check the module,
       power supply, CAN communication, ignition state and required adapter/cable
       before attempting alignment.
   * - False
     - True
     - A module is responding on the network but is not configured as present. This
       can occur after a retrofit, module installation or incorrect vehicle
       configuration and can cause a PROXI mismatch.
   * - False
     - False
     - The module is neither configured as installed nor currently detected. This can
       be a normal state for optional equipment that is not fitted.

Before starting an alignment
----------------------------

Before pressing the execute button:

* set the ignition to ON / RUN as instructed by JScan,
* keep the engine OFF unless the application explicitly says otherwise,
* make sure the vehicle battery voltage is stable,
* use the required OBD adapter and CAN adapter cable if indicated,
* make sure all modules that should be present are communicating,
* do not disconnect the OBD adapter or switch the ignition off while configuration
  data is being written.

If ``Module Present`` and ``Module Active`` do not agree, investigate the reason before
starting the alignment. PROXI Alignment cannot repair a module that is offline or a
physical CAN communication fault.

Screen controls
---------------

The PROXI Alignment screen contains two main controls:

**Refresh**
   Reads the vehicle again and refreshes the module, EOL and cable-adapter status.

**Execute**
   Starts the PROXI Alignment procedure and writes the required configuration to the
   modules that participate in the alignment.

After a completed procedure, follow the ignition-cycle instructions displayed by JScan,
reconnect if required and refresh the PROXI Alignment screen. Modules that require EOL
synchronization should then report the correct EOL status.


How to perform PROXI Alignment
------------------------------

PROXI Alignment may need to be performed on modules located on different CAN networks.
Because of this, some modules can be aligned using the adapter directly, while others
require a coloured cable adapter.

The procedure should be performed in stages.

1. Open::

      Body -> Service Procedures -> PROXI Alignment

2. Perform PROXI Alignment for all modules that **do not require a coloured cable**.

   Run the alignment for every module that can be accessed using the current adapter
   connection.

   .. note::

      The information shown on the PROXI Alignment screen may not update immediately
      after each successful alignment. This is normal. Do not repeat a successful
      alignment only because the displayed status has not changed yet.

3. Disconnect the OBD adapter from the vehicle.

4. Connect the adapter again using the **grey cable**.

5. Perform PROXI Alignment for all modules that require the **grey cable**.

6. Disconnect the OBD adapter again.

7. Connect the adapter using the **blue cable**.

8. Perform PROXI Alignment for all modules that require the **blue cable**.

9. Disconnect the adapter from the vehicle.

10. Cycle the ignition:

    * switch the ignition OFF,
    * wait a few seconds,
    * switch the ignition back ON.

11. Reconnect JScan to the vehicle.

12. Open::

       Body -> Service Procedures -> PROXI Alignment

13. Refresh the module status.

    All modules that participate in the PROXI configuration should now report the
    correct status.

.. important::

   Always follow the cable information displayed by JScan for each module. Not every
   vehicle uses all cable types, so only connect a coloured cable when JScan indicates
   that it is required.

When PROXI Alignment should be performed after adaptations
----------------------------------------------------------

You do **not** need to perform PROXI Alignment after every single adaptation.

Several vehicle configuration changes can be made first, and PROXI Alignment can then
be performed once after all required adaptations have been completed.

However, if any of the changes require PROXI synchronization, the alignment must be
completed **before the vehicle is returned to normal use or driven**.

A typical workflow is therefore::

   make adaptation
   make another adaptation
   make additional required changes
   perform PROXI Alignment
   cycle the ignition
   reconnect and verify the module status

This avoids unnecessary repeated PROXI procedures while still ensuring that the vehicle
configuration is synchronized before the vehicle is used normally again.

Do not drive the vehicle with an unfinished PROXI configuration when the performed
adaptations require alignment. Some modules or vehicle functions may remain unavailable
or operate incorrectly until the synchronization has been completed.
