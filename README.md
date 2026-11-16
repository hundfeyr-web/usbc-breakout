# USB-C to 3.3 V Breakout

A small 2-layer breakout board designed in KiCad. It takes 5 V from a USB-C port and gives a regulated 3.3 V on a 3-pin header.

This is the first design I've posted. It has not been fabricated or tested, and I don't plan to build it, so feedback on the design is welcome (see [Status](#status)).

![Top view](images/usbc-breakout.png)

## Features

- USB-C receptacle input (USB 2.0, 16-pin)
- 5.1 kΩ resistors on CC1 and CC2 so a USB-C charger supplies 5 V
- AP2112K-3.3 LDO regulator with input and output capacitors
- 3-pin header: +5V, +3V3, GND
- 30 x 25 mm, 2 layers, GND copper pour on both layers

## Bill of materials

| Ref | Value | Part | Qty |
|-----|-------|------|-----|
| J1 | USB-C receptacle | Palconn UTC16-G (16-pin, USB 2.0) | 1 |
| U1 | 3.3 V LDO | AP2112K-3.3 (SOT-23-5) | 1 |
| C1, C2 | 1 µF | Capacitor (C1 input, C2 output) | 2 |
| C3 | 100 nF | Output capacitor | 1 |
| R1, R2 | 5.1 kΩ | CC1 and CC2 resistors | 2 |
| J2 | 1x03 | Pin header (+5V, +3V3, GND) | 1 |

## Files

- `*.kicad_pro`, `*.kicad_sch`, `*.kicad_pcb`: KiCad project, schematic and board
- `images/`: 3D renders
  - `usbc-breakout.png`: top view
  - `2.png`: front view
  - `3.png` and `4.png`: side views
  - `5.png`: back view

## Design notes

- **Connector:** J1 is rotated 180° so its "PCB Edge" line sits on the top board edge.
- **Symbol and footprint mismatch:** my first USB-C connector symbol did not match the footprint, which caused a pile of DRC errors. Switching to the 16-pin Palconn UTC16-G symbol and footprint fixed it.
- **Ground fill:** GND zones on F.Cu and B.Cu with 0.3 mm clearance and solid pad connections. The fill left a few isolated copper islands, so I added vias to tie them back to GND.
- **Copper to hole clearance:** I lowered it to 0.2 mm in the board setup so J1's mounting pegs pass DRC. Check this against your fab's minimum before ordering. It may need to be raised or the footprint adjusted.
- **Silkscreen:** I turned off the "silkscreen clipped by board edge" DRC warning.
- **DRC:** 0 violations, 0 unrouted items.

## Status

- Schematic and layout finished, DRC clean
- Not fabricated or tested, and I don't plan to fabricate it
- Feedback on the design is welcome: please open an issue or message me

## Author

Hundaol Feyera  
[LINKEDIN_LINK](https://www.linkedin.com/in/hundaol-feyera-5a99b93a8?utm_source=share_via&utm_content=profile&utm_medium=member_android)

## License

MIT
