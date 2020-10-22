###############
Troubleshooting
###############

JScan doesn't read the VIN

	1. Make sure the key is in ON position (not ACC) – i.e. dashboard controls are on.
	2. Inspect the OBD adapter and socket. Do pins fit tight? Or are they loose / dirty / rusty / broken?
	3. Go to JScan settings (cog, top-right corner) > ELM327 identification. All entries except ABS are adapter-phone communication. ABS is adapter-car. Any “false" values will indicate a possible adapter issue.
	4. If it’s a new purchase use “Return and Replace" or similar method to get another device from the vendor.

	.. attention:: Do NOT purchase the license as a “fix". The license has nothing to do with the communication between the devices.

Tire Size adaptation - check engine light and speedometer not working.

	Was the adaptation done with engine working?

	If yes, open “Quick Diagnostic" page and tap “Trash" icon. Engine must be OFF and Ignition must be ON (usually second key position). All should be back to normal.

	If not, (that is, if adaptation was done with key ON, engine OFF), you probably typed the tire size manually. However, the manual input here is for circumference (in mm), NOT the diameter (height). So, either do the math (tire height inches * 2.54 * PI) and type the result in manual input, or – recommended – use the drop down to find the closest value matching tire height (in).

	..note:: Factory speedometer is ALWAYS showing higher reading than you actually drive. That’s a safety feature, required legally for example in the EU. If you want to ‘fix’ it, just pick a slightly smaller tire height (0.25"-0.5" less than real).