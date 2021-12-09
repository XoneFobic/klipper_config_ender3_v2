# Klipper Config for XoneFobic's Ender 3 v2

## SLICER

As I use superslicer, all settings in this section are aimed for it.  
Convert them as needed to your slicer of choice.

### Print Settings

As I enable ArcWelding in the klipper settings, I also add it to the `Post-processing script` in the `Output options` section.  
Look in the docs of the ArcWelder script you're using to know what to apply here.  
I use the Windows version of [ArcWelderLib](https://github.com/FormerLurker/ArcWelderLib) by FormerLurker. In this case just add `C:\path\to\bin\ArcWelder.exe` to the `Post-processing script` section.

### Filament Settings

#### Start G-code
Obviously, change these values as needed.  
```
; Polymaker Polylite PLA
SET_PRESSURE_ADVANCE ADVANCE=0.0275
```

### Printer settings

Within the `General` tab, make sure to turn on `Use relative E distances`. The `START_PRINT` and `PRIME_LINE` macro are set up to be relative instead of absolute.  
  
#### Start G-code
```
START_PRINT BED_TEMP=[first_layer_bed_temperature] EXTRUDER_TEMP={first_layer_temperature[initial_extruder]+extruder_temperature_offset[initial_extruder]}
```

#### End G-code
```
END_PRINT
```

#### Before layer change G-code
```
;BEFORE_LAYER_CHANGE
G92 E0
;{layer_z}
```

## MODS
### Applied Mods that could affect settings / print quality

* BLTouch
* Direct Drive Conversion
    * Dragonfly BMS ([Phætus](https://www.phaetus.com/dragonflybms/))
    * Orbiter v1.5 Extruder ([Thingiverse](https://www.thingiverse.com/thing:4725897) | [AliExpress](https://www.aliexpress.com/item/1005002071694186.html)) __Make sure to get the LDO stepper!__
    * Custom Voron Afterburner _(Repo will be added once the STEP files are clean)_
* Copper plated nozzle ([Phætus](https://www.phaetus.com/plated-copper-nozzle/) | [Duckleberry (Netherlands)](https://www.duckleberry.nl/accessoires/nozzles/koperen-nozzle-voor-e3d-v6-0-4mm/))
* 50W heater cartridge ([AliExpress](https://www.aliexpress.com/item/4000550325460.html))
* 10HT500T based thermostat (Max 500°C) ([AliExpress](https://www.aliexpress.com/item/4000591370691.html))
* Smooth PEI Flex Plate ([AliExpress](https://www.aliexpress.com/item/1005002953320470.html))
* Yellow dot squash ball feet

### Mods in progress

* Voron Switchwire conversion

### Planned Mods

* Belt conversion (Lead Screw Delete) ([Thingiverse (Original)](https://www.thingiverse.com/thing:4243512) | [Thingiverse (Beefy Upgrade)](https://www.thingiverse.com/thing:4713139))
* Upgraded mainboard
* New wire harness
* Reprint all printed parts in ABS or ASA
* Enclosure

### Retired Mods

* Voron M4 ([VoronDesign](https://vorondesign.com/voron_m4))
    * Voron M4 Direct Drive conversion ([Thingiverse](https://www.thingiverse.com/thing:4901100))