Jeep Wrangler JL/JT 2018+ Rear Lights Conversion US to EU
==========================================================

This procedure describes the general steps required to convert rear lamps
on Jeep Wrangler JL/JT 2018+ from US specification to EU specification.

The conversion usually includes:

* separating rear brake lights from rear turn signals,
* enabling dedicated rear turn signal outputs in the BCM,
* adding missing wires between the BCM and rear lamps,
* installing EU specification rear lamps,
* enabling rear fog lamp outputs,
* replacing the light switch with an EU specification version when rear fog lamps are required.

.. warning::

   This procedure requires physical wiring modifications.
   OBD JScan can only change the vehicle configuration.
   It cannot replace missing wires, connectors, lamps, or switches.

.. warning::

   Always verify the wiring diagram for the exact vehicle year, body type,
   trim level, and lamp package before modifying the vehicle wiring.
   Incorrect wiring may damage the BCM or lighting components.

Required Parts
--------------

Depending on the vehicle equipment and the scope of conversion, the following
parts may be required:

* EU specification rear lamps,
* additional wires from BCM to rear lamps,
* BCM terminal pins,
* KOSTAL 2.8 SLK terminals for rear turn signal outputs,
* KOSTAL 1.2 MLK / SLK terminals for rear fog lamp outputs,
* EU specification light switch with rear fog lamp function,
* suitable OBD adapter supported by OBD JScan.

BCM Location
------------

The Body Control Module, also called BCM or Body Computer, is located on the
passenger side, behind the side panel under the glove box.

Rear Turn Signal Conversion
---------------------------

US specification rear lamps may use combined brake and turn signal operation.
For EU specification, the rear brake lights and rear turn signals must work
as separate outputs.

Configuration Changes in OBD JScan
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Open the vehicle configuration/adaptation section in OBD JScan and change the
following settings:

.. list-table::
   :widths: 40 25 35
   :header-rows: 1

   * - Setting
     - Required Value
     - Description
   * - Combined Rear Lighting
     - Deactivated
     - Disables combined brake/turn operation. The rear brake lamp remains brake-only.
   * - Rear Turn Lamps Output Present
     - Activated
     - Enables dedicated rear turn signal outputs in the BCM.

BCM Pins for Rear Turn Signals
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After activating ``Rear Turn Lamps Output Present``, the BCM outputs for the
rear turn signals become available on the following pins:

.. list-table::
   :widths: 30 20 50
   :header-rows: 1

   * - BCM Connector
     - Pin
     - Function
   * - C5 / E, Black connector
     - 3
     - Rear turn signal output
   * - C6 / F, White connector
     - 42
     - Rear turn signal output

Use suitable terminals for the BCM connector.

Required terminal type:

.. code-block:: text

   KOSTAL 2.8 SLK

Wiring
~~~~~~

Add two new wires from the BCM to the rear lamps:

* one wire from BCM connector C5/E pin 3,
* one wire from BCM connector C6/F pin 42.

Connect the new wires to the dedicated turn signal input of each EU rear lamp.

.. note::

   The rear lamp connectors are usually the same, but the EU lamp requires
   an additional wire for the separate turn signal function.

Lamp Diagnostics and LED Configuration
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After installing the EU rear lamps, additional configuration may be required
to remove bulb warning messages or lamp diagnostic errors.

The exact settings depend on the vehicle equipment, especially whether the
vehicle has LED or non-LED rear lamps.

Typical settings to verify:

* LED Rear Turn Lamps,
* LED Stop Lamps,
* Left Rear Turn Lamp Diagnostic Present,
* Right Rear Turn Lamp Diagnostic Present,
* other rear lamp diagnostic settings related to the installed lamp type.

.. note::

   These settings are vehicle-specific. If warning messages remain after the
   conversion, check LED/non-LED configuration and lamp diagnostic options.

Rear Fog Lamp Conversion
------------------------

EU specification vehicles normally require rear fog lamps. This requires both
configuration changes and additional wiring.

Configuration Changes in OBD JScan
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Enable the rear fog lamp outputs:

.. list-table::
   :widths: 40 25 35
   :header-rows: 1

   * - Setting
     - Required Value
     - Description
   * - Rear Fog Lamps Output Present
     - Activated
     - Enables rear fog lamp outputs in the BCM.

BCM Pins for Rear Fog Lamps
~~~~~~~~~~~~~~~~~~~~~~~~~~~

After activating ``Rear Fog Lamps Output Present``, the rear fog lamp outputs
are available on the following BCM pins:

.. list-table::
   :widths: 30 20 50
   :header-rows: 1

   * - BCM Connector
     - Pin
     - Function
   * - C5 / E
     - 39
     - Rear fog lamp output
   * - C6 / F
     - 5
     - Rear fog lamp output

Required terminal type:

.. code-block:: text

   KOSTAL 1.2 MLK / SLK

Wiring
~~~~~~

Add the required wires from the BCM to the rear fog lamp circuit:

* BCM connector C5/E pin 39,
* BCM connector C6/F pin 5.

Connect the wires to the rear fog lamp circuit according to the vehicle wiring
diagram and the installed EU rear lamp type.

Light Switch
~~~~~~~~~~~~

To operate the rear fog lamps, replace the light switch with an EU specification
version that includes rear fog lamp control.

Final Verification
------------------

After completing the coding and wiring work:

#. Cycle the ignition off and on.
#. Check rear brake lights.
#. Check left and right rear turn signals.
#. Check hazard lights.
#. Check rear fog lamps.
#. Check for bulb warnings on the instrument cluster.
#. Scan all modules for DTCs.
#. Correct LED/non-LED and diagnostic settings if warning messages remain.

Troubleshooting
---------------

Rear turn signals do not work
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Check the following:

* ``Rear Turn Lamps Output Present`` is set to ``Activated``.
* ``Combined Rear Lighting`` is set to ``Deactivated``.
* The new wires are installed in the correct BCM pins.
* BCM terminals are fully seated in the connector.
* EU rear lamps are connected correctly.
* LED/non-LED settings match the installed lamps.

Brake lights work together with turn signals
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Check that ``Combined Rear Lighting`` is set to ``Deactivated``.

Bulb warning message is displayed
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Check lamp diagnostic settings and LED/non-LED configuration. Depending on the
lamp type, rear turn lamp diagnostics may need to be enabled or disabled.

Rear fog lamps do not work
~~~~~~~~~~~~~~~~~~~~~~~~~~

Check the following:

* ``Rear Fog Lamps Output Present`` is set to ``Activated``.
* The rear fog lamp wires are installed in the correct BCM pins.
* The vehicle has an EU specification light switch with rear fog lamp support.
* Rear fog lamp wiring and lamp ground are correct.

Summary
-------

OBD JScan can activate the BCM outputs required for EU rear lamp conversion,
but the vehicle must also be physically modified. The conversion requires
correct BCM coding, additional wires, correct BCM terminals, EU rear lamps,
and in the case of rear fog lamps, an EU specification light switch.


    .. image:: ../img/bcm/bcm_connector_overview.png
	:width: 200px

    .. image:: ../img/bcm/bcm_pin_slk_12.png
	:width: 200px

    .. image:: ../img/bcm/bcm_pn_slk_28.png
	:width: 200px