#############################
Module replacement procedures
#############################

.. warning:

	This guide (just like the app and the docs in general) is provided AS IS. We are not responsible nor will be held liable for any damages, errors, losses, issues etc.

	PROCEED AT YOUR OWN RISK (AND RESPONSIBLITY)



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