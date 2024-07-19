##################
User manual
##################

(work in progress)

This section explains the functions and features of the app. For specific modification guides pelase see the How To and Model-Specific sections.


********
Settings
********

The settings menu is accessible through a cog wheel icon in the top right corner of the app and contains the following options:

App & Adapter settings
======================

General app and connection configuration. Notable settings here include the unit system (imperial/metric), showing advanced adaptations / features, and experimental vehicles. Do not modify unless you really know what you're doing.

Manage Licenses & Account
=========================

Here you can buy additional licenses (BUY) and see your current license (STATUS), and the **Account Token**.
See the `Licensing`_ section for details.

Get Help
=========

Various help resources / links.

Send data log via e-mail
========================

For app development purposes only. We might ask for this log when debugging issue and solving problems. Please do not send unsolicited logs - we don't have the capacity to handle them.

Trail View settings
===================

Configuration for the Trail View. Can also be accessed from the Trail View itself.

Garage Account
==============

As the name suggests: option available to garages only. Used to manage bulk licensing. Contact us via Facebook's Messenger if you run a workshop and are interested in setting up such account.

Restore Purchases
=================

WIP: Retrieve purchase info from the app store.

Trace & Restore Adaptations
===========================

Change log and backup.

ELM327 - Identification
=======================

Adapter compatibility test - checks basic OBD adapter functionality. 

All green is good, but doesn't mean the adapter will be 100% compatible. Check the list of `compatible adapters`_.

All red is not good - most likely your adapter is incompatible or damaged.

Certain elements in red are OK - if the adapter works as intended, there's no need to start troubleshooting based on the ELM327 Identification report.

OBD Terminal
============

Normally hidden (can be enabled in App & Adapter settings). **VERY** advanced, not designed fo regular use. We don't provide any support for it whatsoever.

Privacy Policy
==============

Legal stuff - the most important part is that any change / modification / interaction with the vehicle is YOUR responsibility. JScan is not a toy. It can permanently damage your vehicle if used without care and proper research.


***********************
Dashboard (main screen)
***********************

Quick Diagnostic
================

This screen is responsible for displaying "generic" - "check engine light" Trouble Codes. No license required.

Live Data
==========

This screen will dispay "generic" live data - live data that is common across multiple cars and models.

..note :: Quick Diagnostic and Live Data available on main screen are generic (standard) data available on almost all cars and models to allow an independent technician to diagnose a car - this is how 99% of cheap OBD tools work.

Advanced Scan
=============

A more detailed error scan. It will go through all the available modules on the car and query for DTCs (diagnostic trouble codes).

To clear the errors, press the trash can icon.

.. note:: Advanced Scan and code clearing does NOT solve the reason why errors occur.

There are different error statuses - the status is written jut below the error code

- **stored:** the error occurred in the past and usually is not present anymore. In most cases, this type of error will be permanently deleted when you clear error codes
- **active:** the error is currently reported by the car. In most cases, this error will come back after clearing error codes
- **permanent:** Permanent codes are additional codes. Stored in special memory on PCM ECU, usually they are not showing on most diagnostic tools as they are only used by services in special case. That's why only some tools like JScan will put additional effort to display this additional info.
- **pending:** the vehicle diagnostic systems encountered a possible problem, which may turn into active or permanent in the future, if following diagnostic cycles run into it again. Think of it as a warning about future issues.


.. note:: FYI: We are not able provide advice on fixing either mechanical or electrical issues with your car, so a question "how do I fix code XYZ?" should rather go to your car mechanic.



********
Modules
********

This screen shows all **possible** modules for this model - it doesn't mean that are all actually installed on this particular car.

Each module has 3 functionalities:

1) Trouble Codes: Allows you to show/clear - Trouble Codes on currently selected module

2) Live Data : Shows live data for currently selected module - you need to select the PIDs you want and **press PLAY** to start showing data for this module.

3) Activations: Triggers module functions / control signals.

4) Configuration: Module's configurable options.

For details on Activations and Configuration please see the `Modifying your vehicle`_.


***********
Adaptation
***********

This screen will show a pre-build adaptation list (configuration, settings changes) for this particular model.

**The Search** button is available on bottom - we are trying to group related settings but this is not always possible.

For details please see the `Modifying your vehicle`_.

***********************************
Trail View / Drag View / TPMS View
***********************************

Additional screens available on certain models with extra features.

See `Trail View`_ for details.




.. _compatible adapters: http://jscan.net/supported-and-not-supported-obd-adapters/
.. _Modifying your vehicle: https://jscan-docs.readthedocs.io/en/latest/general/modifications.html
.. _Licensing: https://jscan-docs.readthedocs.io/en/latest/general/license.html
.. _Trail View: https://jscan-docs.readthedocs.io/en/latest/general/trail_view.html