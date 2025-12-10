#############################
Module replacement procedures
#############################

.. warning:

	This guide (just like the app and the docs in general) is provided AS IS. We are not responsible nor will be held liable for any damages, errors, losses, issues etc.

	PROCEED AT YOUR OWN RISK (AND RESPONSIBLITY)


Procedure: Adapting a used ABS
====================================================

Overview:
--------
This procedure outlines the steps required to install a used ABS module in a vehicle using the application.

.. note::

   This method may not be suitable for every model and or year. Always consult a service manual.


Steps:
------

The general steps are as follows:

#. Make sure the ABS module installed matches the *exact* part number of the original.
#. Make sure there are no ABS-related errors in Advanced Scan, except for Vehicle Configuration Mismatch.
#. In the Adaptations > Vehicle Maintenance run the ABS - Clear VIN Original and Current
#. Turn the ignition to off
#. After a few minutes, turn the ignition to RUN, as usual. Do NOT start the engine.
#. Connect with JScan again.
#. In the Adaptation > Vehicle Maintenance run the ABS - Initialization (or Full Initialization)
#. Once complete, cycle the ignition (steps 4,5), connect, check the Modules > ABS for the new VIN and run Advanced scan.

Troubleshooting:
----------------

The above will NOT work if:

- the part number of the replacement module is different
- there are other ABS errors



Procedure: Adapting a Used BCM (Body Control Module)
====================================================

Overview
--------

This procedure describes the steps required to adapt and configure a used BCM module in a vehicle using the application.

.. note::

   This method applies primarily to vehicles produced up to approximately **model year 2017**, equipped with BCMs **not protected by the Security Gateway (SGW)** system.

   Starting around **2017**, newer BCMs include enhanced security protections that prevent direct copying or restoring of configuration data. For these later modules, configuration must be performed manually.

1. Create a Backup of the Original BCM Settings
-----------------------------------------------

Before replacing the BCM, create a full backup of the configuration data from the existing (original) module.

#. Open the **application settings**.  
#. Go to the **Trace Entry** tab.  
#. Select the **Store** option.  
#. Under the **Restore** tab, tap the **three dots menu (⋮)** and choose **Start Backup**.  
#. Wait until the backup process is completed.

This backup will be used later to restore all original configuration values to the replacement BCM.

2. Install the Replacement BCM
------------------------------

Once the backup is complete, physically install the replacement (used) BCM module in the vehicle.

3. Prepare the New BCM for Configuration
----------------------------------------

#. Connect to the vehicle using the application.  
#. Navigate to the **Body Module (BCM)**.  
#. Open **Configuration**.  
#. Set the **Vehicle Configuration Status** option to **False**.

This step enables reconfiguration of the module.

4. Perform Configuration Reset Procedures
-----------------------------------------

Next, perform two adaptation procedures within the **Adaptation** menu:

- **Reset Configuration**
- **Engineering Configuration Reset**

Run both procedures in the order listed above.

5. Restore the Original Settings
--------------------------------

After completing both resets:

#. Go back to the **application settings**.  
#. Select **Restore**.  
#. Choose the previously created backup.  
#. Restore all settings to the new BCM.

6. Cycle the Ignition
---------------------

After the restore process is complete:

- Switch the ignition **OFF**, wait a few seconds, and then turn it **back ON (RUN position)**.  
- This ensures that the BCM reloads all configuration parameters properly.

7. Finalize Configuration
-------------------------

Reconnect to the BCM module, go to **Configuration**, and set the **Vehicle Configuration Status** option to **True**.  

This final step confirms and locks in all configuration data on the new module.