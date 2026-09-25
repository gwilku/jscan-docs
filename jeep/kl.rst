Quick info
==========

Cherokee KL platform is supported, but you need to know the following:

1. They are Fiats with a Jeep badge, and have a completely different software and different customisation options.
2. You need to perform PROXI alignment after making changes (research it online please), which:
3. requires vLinker MC+ (Cherokee) or vLinker MS (Renegade and Compass), as theese are the only reliable OBD adapters that can perform PROXI, and even then in certain cases a special blue OBD cable might be required.
4. If you acknowleddge the above, you can go to JScan settings > app & adapter settings > and enable 'show experimental vehicles'. 

And we highly encourage you to do it first, and explore the vehicle options in Demo mode (especially see PROXI and it's description) before investing in a license and adapter.

In addition, as with all other 2018+ vehicles from Stellantis, you will need a Security Gateway Bypass cable.

PROXI Alignment
===============

After you make the desired changes (adaptations), the vehicle configuration must be uploaded to all controlling modules. This is called PROXI alignment, and is done as follows:

`PROXI Alignment documentation <https://jscan-docs.readthedocs.io/en/latest/general/proxi_alignment.html>`_

* go to PROXI alignment adaptation
* execute all PROXI alignments for modules that *DO NOT* require a coloured cable
* don't worry when the information is not updated correctly immediately - this is normal
* unplug the adapter and plug it back in with the grey cable
* perform PROXI adaptations on modules that require the gray cable
* unplug the adapter and plug it back in with the blue cable
* perform PROXI adaptations on modules that require the blue cable
* disconnect
* cycle the ignition
* reconnect
* open PROXI alignment adaptation: all modules should be good to go

This procedure must be performed before driving the car, so you can make more than one adaptation before doing the PROXI alignment. In other words, there is no need to do the PROXI alignment after every single adaptation, but you must do it when you want the car to be fully operational again.

Separate Rear Turn Signal Wiring
===================================================

Overview
--------

Some Jeep Cherokee KL configurations use combined rear stop and turn signal
outputs. In this configuration the same rear lamp function is used for both
braking and turn indication.

To convert the vehicle to separate rear stop lamps and rear turn signals,
the BCM configuration must first be changed and two additional wires must
be installed between the Body Control Module and the rear lamp assemblies.

The original stop lamp wiring remains unchanged.


Step 1 - Disable Combined Rear Lights
-------------------------------------

Open the BCM adaptations in JScan and disable:

**Combined Rear Lights**

This setting must be disabled before using the dedicated rear turn signal
outputs.

When ``Combined Rear Lights`` is enabled, the BCM uses the rear stop lamp
outputs for both braking and turn indication.

After disabling this option, the BCM can use the dedicated:

* Left Rear Turn Lamp Driver
* Right Rear Turn Lamp Driver

outputs.


Step 2 - Add the rear turn signal wires
----------------------------------------

The dedicated rear turn signal outputs are available directly from the BCM.

Two additional wires must be installed:

.. list-table:: Rear turn signal wiring
   :header-rows: 1
   :widths: 22 18 18 18 24

   * - Function
     - BCM connector
     - BCM pin
     - Circuit / color
     - Tail lamp pin
   * - Left Rear Turn Lamp
     - C6
     - 2
     - L63 - WH/DG
     - 2
   * - Right Rear Turn Lamp
     - C4
     - 30
     - L62 - WH/YE
     - 2

Wire color abbreviations:

* ``WH/DG`` - White / Dark Green
* ``WH/YE`` - White / Yellow

The new wires should therefore be connected as follows:

**Left side**

::

   BCM C6 pin 2
       |
       |  L63 - WH/DG
       |
       +--------------------> Left Tail Lamp pin 2
                               LEFT REAR TURN LAMP DRIVER

**Right side**

::

   BCM C4 pin 30
       |
       |  L62 - WH/YE
       |
       +--------------------> Right Tail Lamp pin 2
                               RIGHT REAR TURN LAMP DRIVER


Existing stop lamp wiring
-------------------------

The existing stop lamp wiring must remain connected.

According to the factory wiring diagram:

.. list-table:: Existing stop lamp wiring
   :header-rows: 1
   :widths: 28 18 24 20

   * - Function
     - BCM pin
     - Circuit / color
     - Tail lamp pin
   * - Left Stop Lamp Driver
     - 48
     - L52 - WH
     - 1
   * - Right Stop Lamp Driver
     - 17
     - L54 - WH/GN
     - 1

After the modification each rear lamp therefore has separate control inputs:

* **Pin 1** - Stop Lamp Driver
* **Pin 2** - Rear Turn Lamp Driver


Rear lamp fault detection
-------------------------

No additional fault detection wire is required.

The stop lamp driver and the rear turn lamp driver use the same rear lamp
fault-sense circuit.

For the left rear lamp:

::

   Tail Lamp pin 4
       |
       |  L563 - WH/GY
       |
       +--------------------> BCM
                               LEFT REAR LIGHTING FAULT SENSE

For the right rear lamp:

::

   Tail Lamp pin 4
       |
       |  L562 - WH/BG
       |
       +--------------------> BCM
                               RIGHT REAR LIGHTING FAULT SENSE

This means that the existing fault-sense wiring should not be modified when
adding the dedicated turn signal wires.

The rear lamp assembly internally uses the same fault-detection circuit for
both the stop lamp and turn signal functions.


Rear lamp connector summary
----------------------------

After the modification the relevant connections at each rear lamp are:

.. list-table::
   :header-rows: 1
   :widths: 15 35 50

   * - Pin
     - Function
     - Modification
   * - 1
     - Stop Lamp Driver
     - Existing wire - leave unchanged
   * - 2
     - Rear Turn Lamp Driver
     - New wire from BCM
   * - 4
     - Rear Lighting Fault Sense
     - Existing wire - leave unchanged
   * - 5
     - Ground
     - Existing wire - leave unchanged


Final result
------------

After the modification the BCM controls the rear lighting functions
independently:

::

                  LEFT REAR LAMP

   BCM Stop Driver ---------> Pin 1 ---- Stop Lamp
   BCM Turn Driver ---------> Pin 2 ---- Turn Signal
   BCM Fault Sense <-------- Pin 4 ---- Lamp Fault Detection
   Ground ------------------> Pin 5


                  RIGHT REAR LAMP

   BCM Stop Driver ---------> Pin 1 ---- Stop Lamp
   BCM Turn Driver ---------> Pin 2 ---- Turn Signal
   BCM Fault Sense <-------- Pin 4 ---- Lamp Fault Detection
   Ground ------------------> Pin 5

The important point is that the original stop lamp and fault-sense circuits
remain in place. Only the dedicated left and right rear turn signal driver
wires need to be added.

.. important::

   Verify the BCM connector and terminal positions before inserting new
   terminals. Connector numbering and wiring may differ between vehicle
   production years and market versions.

   After changing the BCM configuration, cycle the ignition and verify the
   operation of the left turn signal, right turn signal and brake lamps
   independently.