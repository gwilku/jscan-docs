.. jscan-docs documentation master file, created by
   sphinx-quickstart on Thu Aug 27 18:20:00 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

###########################
JScan Documentation Project
###########################
.. title:: JScan documentation project.

*****************
What is OBD JScan
*****************

OBD JScan is a mobile-only (Android and iOS) vehicle diagnostics and configuration app, exclusive for Jeep, Dodge, Chrysler and RAM vehicles listed in the app. It uses the vehicles' OBD (On-Board-Diagnostics) Port via one of the `compatible adapters`_.

Features
========

With a proper adapter (and a `security gateway bypass`_ for most 2018-2024 models) the app is able to:

 * read the live data from the supported vehicles' modules
 * read the DTCs (Diagnostic Trouble Codes, a.k.a. "errors")
 * delete the non-pemanent DTCs
 * run the vehicles' service procedures
 * trigger control signals (Activations)
 * **change the vehicle configuration (Adaptations)**.

For some vehicle models, the app provides additional screens like Trail View, TPMS View or similar, with extra features & functionalities. Please see the User Manual section or the vhicle-specific chapter of this documentation for further details.


Limitations
===========

The app does not:

 * connect to the vehicle directly. It requires one of the `compatible adapters`_.
 * **flash** the vehicle modules. (Make sure you `know the difference`_).
 * provide service procedure documentation or guides, and should not be treated as a replacement for a proper service manual.
 * work with other vehicle brands.
 * work with vehicles not listed in the app. 

 .. warning:: Please be aware, that any changes, modifications, and/or service procedures are the Users' (your) responsibility.

*****************
Contents
*****************
.. toctree::
   :maxdepth: 2
   :caption: General

   general/getting_started
   general/user_manual
   general/license
   general/modifications
   

.. toctree::
   :maxdepth: 2
   :caption: ❗ Troubleshooting

   general/troubleshooting


.. toctree::
   :maxdepth: 2
   :caption: 💡 How To's

   general/tpms
   general/drl
   general/led
   general/tiresize
   general/key_programming
   general/nag1
   general/etc
   general/acc
   general/service_procedures
   general/radio
   general/module_replacement
   general/comunity_videos

.. toctree::
   :maxdepth: 2
   :caption: Model-Specific features

   jeep/jeep
   dodge/ram
   dodge/dodge
   chrysler/chrysler

.. toctree::
   :maxdepth: 2
   :caption: Miscellaneous

   general/glossary
..   general/testimonial   

..   jeep/jk
   jeep/jl
   jeep/jt


Downloading the docs
======================

It is possible to download the whole documentation for off-line use - see the bottom left corner (click on Read the Docs with the book icon), but be aware that this documentation is being constantly updated.


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`



.. _compatible adapters: http://jscan.net/supported-and-not-supported-obd-adapters/

.. _know the difference: https://www.vehicleservicepros.com/service-repair/article/55363484/clarifying-the-difference-module-flashing-coding-and-adaptation-procedures

.. _security gateway bypass: http://jscan.net/jl-jt-security-bypass/