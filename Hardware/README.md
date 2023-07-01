# This is __The Nerd Mage Module Programmer__  Project

Each of the subfolders here is basically a KiCAD project.  Yes, I know there's a lot of duplication here.  One of these days, I'll figure out how to make KiCAD re-use existing schematics & board files as "libraries".

- (KiCAD Customs)
  - Custom symbols, footprints, 3D models needed for this project
    - (Just the 3D models so far...)

## Notes about the boards common design

### The __reset / io0__ circuit
Transistors Q1 & Q2 are a bright idea stolen blatantly from the schematic of the Wemos D1-mini.  Basically, they cause io0 to be held low during a reset called for programatically.

So...  You can treat these programmers as nodemcu boards.

- In platformio.ini:
  - `upload_resetmethod = nodemcu`
### The LEDs:
- D1
  - indicates power to the board (From USB...)
- D1
  - Indicates power to the module being programmed

### The switches:
- SW1 (pushbutton)
  - Pulls the reset line of the module low
- SW2 (slider)
  - Switches on/off power to the module

### The "Base Plate" board:
The flexyPins used for connecting the modules require space under the board.

So...  The base plate, along with 6 3mmx4mm spacers & 12 of the shortest available 3mm machine screws provide this space & protect the FlexyPins.

## The various "editions"...

- (blank)
  - The base design with no module set up
- (standalone)
  - A version with a pin header instead of a module
- ESP-01F
  - Footprint added for an ESP-01F
- ESP-01S
  - Footprint added for an ESP-01S
- ESP-M3
  - Footprint added for an ESP-M3
- ESP-12
  - Footprint added for an ESP-12 (or ESP-07)
- ESP-Wroom-32
  - Footprint added for an ESP-Wroom-32
- BOM.ods
  - Sort of a manually created Bill of Materials

  ## To be done

  Need to work out how to add my custom symbols, footprints & 3D models in here...
  