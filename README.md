# Tesla K20c → GTX Titan Conversion

This repository contains the BIOS file I used to turn a Tesla K20c into a GTX Titan.  
The full process, including disassembly, cooling work, flashing, and testing, is shown in my own video linked below.

Video: https://www.youtube.com/watch?v=Yx7tkJtUpDI

The goal of this mod is to unlock regular 3D graphics and gaming support on the K20c, which normally only exposes compute functionality.

---

## What’s in this repo

- `k20_modded_bios_to_titan.rom`  
  This is the exact BIOS I flashed in the video.  
  Note: The clocks in this ROM are overclocked. Depending on your card, cooling, and silicon quality, you may need to reduce them.

---

## Flashing method (important)

The K20c cannot be flashed with nvflash.  
The BIOS region is locked, so the EEPROM has to be written directly with a hardware programmer.

I used a CH341A with a SOIC8 clip:

1. Remove the card from the system.
2. Attach the clip to the EEPROM on the PCB (or desolder the chip if you prefer).
3. Make a backup of the original EEPROM contents. Don’t skip this step.
4. Write the provided ROM file to the chip.
5. Reassemble the card and test in your system.

The video shows the entire procedure.

---

## Adjusting clocks and voltages

The BIOS can be edited with **Kepler BIOS Tweaker**.  
If you run into crashes, artifacts, or instability, lower the core clock, boost clock, or memory clock and reflash the modified ROM.

Because this ROM is overclocked, some cards may need more conservative settings depending on cooling and power delivery.

---

## Cooling notes

The fan controll seems to still work quite well. It is way less aggressive compared to the tesla fan curves. With this mods it holds the card temperature at around 80C instead of 65C. 

---

## Driver and performance notes

After flashing, the card shows up as a GTX Titan and loads standard GeForce drivers.  
Performance is close to a real Titan, with some variation depending on clocks, cooling, and the fact that this is still a repurposed Tesla board with fewer FP32 ALUs.

For full details, see the video:

https://www.youtube.com/watch?v=Yx7tkJtUpDI
