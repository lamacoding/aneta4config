# aneta4config

<n>This Software will not be updated anymore. Issues will not be solved!
I do not own the ANET A4 anymore!</b>

<b>New update (v1.2) with better dimensional accuracy! Find the guide for calibrating the dimensions in this readme.</b>

The ANET A4 could be a very nice printer. It has an OK hardware and prints really nicely.
The only thing is: You cannot change ANYTHING! Even the EEPROM is disabled.
As ANET does not provide a firmware to their "open-source" delta-printer, I decided to create my own.
This is compatible with the standard ANET A4 printer, <b>without any modifications</b>.
It's currently based on <b>Marlin 1.1.8</b> (http://marlinfw.org).
You'll need the ANET board library in your Arduino IDE: https://github.com/SkyNet3D/anet-board

<b>You now can calibrate the concave or convex movement that this printer usually has!</b>
  - First of all you should check the rods if they all have the same length (usually they are really precise). That's the most important thing befor you continue!
  - If the rods are correct, find the <i>DELTA_RADIUS</i> in the Configuration.h, which is set to 111mm (that works for me)
  - If the nozzle is too high in the middle of the bed and scratches on the edge: raise the value in 0.5mm steps</p>
  - If the nozzle is too low in the middle of the bed and lifts on the edge: lower the value in 0.5mm steps</p>
  
<b>Calibrate dimensional accuracy:</b>

Usually the Anet A4 has a proportional error (this method <b>only</b> helps against proportional errors! If you have an absolute error, this will not help you.), so the error depends on the part size. E.g. I had a 40mm part which was 41.2mm and a 20mm part that was about 20.6mm. So there was an error of 3% (which is a lot when you need technical parts).
This can be solved easily!
You can do it in 2 ways:
  - Change the value for arm-length (DELTA_DIAGONAL_ROD) in the firmware <b>or</b>
  - Change the value for arm-length in the EEPROM (Menu: Prepare - Delta calibration - Diag rod)
  
  - If your parts are too big, raise the value
  - If your parts are too small, lower the value
  
  Calculating the values is quite easy. If you are off 3%, then change the value for the diagonal rods by 3%.
  I changed the values from 215mm to 220mm in v1.2, this should fit most A4 printers.

<b>Features added:</b>
- EEPROM enabled
- Delta calibration enabled
- changed the button-assignment (middle button is now both MENU- and ENTER-button, the right one now just brings you back to the main screen)
- calibrated steps/mm (originally the extruder was off, I needed 110-120% for extrusion)
- PID tuning added to LCD menu
- no fast fallback to main screen on LCD menu
- Safe homing: all 3 axes will come down a bit after homing to enable safe movements in all directions (do <b>NOT</b> home your printer after a print with G28 unless you know what you're doing. The nozzle is likely to crash into higher prints! Just use something like 'G0 X0 Y0 Z210' to be safe! Or disable safe homing if you want.)
- Reduced DELTA_SEGMENTS_PER_SECOND to 150 to improve performance, now the display should always be working while printing

As the ANET A4 uses mostly the same hardware as the A8 (pulleys, thermistors,...) I was able to get quick results.
Just be <b>careful on first start!</b> Accelerations and feedrates are different from the standard configuration. Just adapt it if you want/need to.

I also included a CAD file of the top frame. ANET delivers a different one than the one in the assembly video. It seems that the "new" one works as well but if you have the possibility to laser-cut acrylic parts, you can use this file. Mine just fits perfectly.
