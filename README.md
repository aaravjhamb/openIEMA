# OpenIEMA

<div align="center">

OpenIEMA is an Open Source, In Ear Monitor Amplifier built as an alternative to the Behringer P2 with dual headphone outputs driven from a mono balanced XLR input, with onboard LiPo power and USB-C charging!!

[![KiCad](https://img.shields.io/badge/KiCad-314CB0?style=for-the-badge&logo=kicad&logoColor=white)](https://www.kicad.org/)
[![Fusion 360](https://img.shields.io/badge/Fusion_360-F6871E?style=for-the-badge&logo=autodesk&logoColor=white)](https://www.autodesk.com/products/fusion-360)
[![XLR](https://img.shields.io/badge/XLR-Balanced_Audio-222222?style=for-the-badge)](#)
[![Blender](https://img.shields.io/badge/Blender-E87D0D?style=for-the-badge&logo=blender&logoColor=white)](https://www.blender.org/)
[![JLCPCB](https://img.shields.io/badge/JLCPCB-00A651?style=for-the-badge)](https://jlcpcb.com/)

</div>

![Hero Render](Renders/openIEMA.png)

## Key Features

- **True balanced input** : Neutrik XLR into an OPA1678 differential line receiver which ensures any long cable runs from the mixer stay noise free
- **Dual 3.5mm outputs** : supports up to two IEM users off one beltpack, driven by a TI TPA6132A2 DirectPath amp!
- **Analog soft limiter** : anti parallel LEDs act as soft limiters that clamp excess noise before you hear it!
- **Fully portable** : Uses a 1S LiPo with USB C charging (MCP73831, 500 mA) and a boost converter to a clean 5 V analog rail, charges while switched off
- **Zero firmware** : 100% analog signal path built for simplicity
- **3D-printed enclosure** : Includes a 3D printed enclosure with volume control all in a compact package!

## PCB

40 × 70 mm, 2-layer, designed in KiCad 10.

**Schematic:**

![](Images/schematic.png)

**Layout:**

![](Images/pcb_layout.png)

**3D View:**

![](Images/3d.png)

## Case

Designed in Fusion 360

![](Images/case.png)

## Credits

This project uses:

- [KiCad 10](https://www.kicad.org/) for schematic capture and layout
- [pcb2blender](https://github.com/30350n/pcb2blender) for the Blender renders
- TI TPA6132A2 + OPA1678, Microchip MCP73831, TI TPS61023

## License

MIT

---

> [aaravj.tech]() · GitHub [@aaravjhamb](https://github.com/aaravjhamb/)
