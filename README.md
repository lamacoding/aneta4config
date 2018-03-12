# aneta4config

The ANET A4 could be a very nice printer. It has an OK hardware and prints really nicely.
The only thing is: You cannot change ANYTHING! Even the EEPROM is disabled.
As ANET does not provide a firmware to their "open-source" delta-printer, I decided to create my own.
This is compatible with the standard ANET A4 printer, <b>without any modifications</b>.
It's currently based on <b>Marlin 1.1.8</b> (http://marlinfw.org).

Features added:
- EEPROM enabled
- Delta calibration enabled
- changed the button-assignment (middle button is now both MENU- and ENTER-button)
- calibrated steps/mm (original the extruder was off, I needed 110-120% for extrusion)
- PID tuning added to LCD menu
- no fallback to main screen on LCD menu

As the ANET A4 uses mostly the same hardware as the A8 (pulleys, thermistors,...) I was able to get quick results.
Just be <b>careful on first start!</b> Accelerations and feedrates are different from the standard configuration. Just adapt it if you want/need to.
