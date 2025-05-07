#############################
LED Lights / Indicators setup
#############################

First steps:
============

 .. note:: TLDR: First change the settings, then install the LEDs.

If you install LED lights - be it headlights, tail lights, indicators, etc., there is a high chance that you will get one of the following:

- fast blinking indicators
- flickering headlights
- no headlights
- no DRL
- light malfunction warning on the dashboard

Vehicle configuration:
======================

Do it **BEFORE** installing LEDs:

- connect to your vehicle with JScan
- go to Adaptations section
- find LED Light settings or a similarly called group, OR, use the search (the green icon with a magnifying glass) and search for LED
- identify settings called "LED <type of light> present ON/OFF" and enable it for every LED light you have

  .. note:: If there is no setting for a given type (i.e. no LED Fog Lights for Wrangler JK) it means the vehicle software is not designed to accomodate for LED lights of a given type. You'll have to install resistors (a.k.a. "anti-flicker harness") or a CAN-compatible LED bulb.

Next, check the following options:

- search for adaptations with the word "diagnostic" or "DTC" and *disable* to disable the persistent trouble code (only in newer vehciles)
- for LED DRLs find an adaptation with the word "voltage" and ensure you set the DRL / LED headlamp volatage to 12-14V (most LEDs will not work at all on lower voltage settings and it's not possible to adjust LED brightness with a lower voltage - this trick works only with traditional bulbs)


Troubleshooting:
================

If the following steps didn't solve the problem of:

- flickering: locate the HID (HIgh Intensity Discharge) Headlights Present, Quad Headlamp Present, and or Bi-Xenon Headlamp present and try if enabling any one or any combination of them eliminates the flickering. If not, you'll need a harness or better quality headlamps
- turn signal (blinker, indicator) hyperflash: ensure you changed the LED Present settings AND disabled diagnostics prior to installing the LEDs. If not, install the original lights again, clear any errors, and repeat the process.