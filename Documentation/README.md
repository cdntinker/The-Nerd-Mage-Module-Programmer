# This is __The Nerd Mage Module Programmer__  Project

Really should expand on this...

## Notes about the common design elements of the boards

### The __reset / io0__ "MCU Mode Select" circuit:
Transistors Q1 & Q2 are a bright idea stolen blatantly from the schematic of the Wemos D1-mini.  Basically, they cause io0 to be held low during a reset called for programatically.

So...  You can treat these programmers as nodemcu boards.

- In platformio.ini:
  - `upload_resetmethod = nodemcu`

### The CH340 UART chip:
This is a basic USB to serial chip.

The version used in the current design (CH340G) uses an external crystal for timing.

__NOTE__ that the RxD & TxD lines from this chip are swapped on their way to the module.

### The USB connector (J1):
These boards use USB-C simply for the convenience of reversability.  The USB connection is actually just USB 2.0.

R3 & R4 are there to ensure that, if your USB port on the computer is USB-C, then 5.0V is supplied to the board.

### The LEDs:
- D1
  - indicates power to the board (From USB...)
- D2
  - Indicates power to the module being programmed

### The switches:
- SW1 (pushbutton)
  - Pulls the reset line of the module low
- SW2 (slider)
  - Switches on/off power to the module

### The "Base Plate" board:
The flexyPins used for connecting the modules require space under the board.

So...  The base plate, along with 6 3mmx4mm spacers & 12 of the shortest available 3mm machine screws provide this space & protect the FlexyPins.
