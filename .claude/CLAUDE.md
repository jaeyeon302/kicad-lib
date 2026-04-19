# KiCad Custom Library

## Purpose
Custom KiCad symbol, footprint, and 3D model libraries.

## Directory Structure

```
kicad-lib/
├── symbols/
│   ├── Custom_{Manufacturer}.kicad_sym   ← dedicated file (5+ parts from same manufacturer)
│   ├── Custom_MCU.kicad_sym              ← misc MCUs from various vendors
│   ├── Custom_Sensor.kicad_sym
│   ├── Custom_Connector.kicad_sym
│   └── Custom_Passive.kicad_sym
├── footprints/
│   ├── Custom_{Manufacturer}.pretty/     ← dedicated (5+ parts)
│   │   └── {PartNumber}.kicad_mod
│   ├── Custom_MCU.pretty/
│   ├── Custom_Sensor.pretty/
│   ├── Custom_Connector.pretty/
│   └── Custom_Passive.pretty/
└── 3dmodels/
    ├── {Manufacturer}/
    │   └── {PartNumber}.step
    └── Misc/
```

## Conventions

- **KiCad version**: KiCad 7+
- **Naming prefix**: all library files and directories are prefixed with `Custom_` to distinguish from KiCad official libraries
- **Manufacturer file threshold**: create a dedicated `Custom_{Manufacturer}.kicad_sym` only when 5+ parts come from the same manufacturer; otherwise use the appropriate category file
- **Symbol naming inside category files**: `{Manufacturer}_{PartNumber}` (e.g., `Bourns_PTV09A`)
- **Symbol naming inside manufacturer files**: `{PartNumber}` only (e.g., `TL071`)
- **Manufacturer/category names**: no spaces, use underscores (e.g., `Texas_Instruments`)
- **Footprint files**: one `.kicad_mod` per part, named by exact part number
- **3D models**: `.step` preferred; `.wrl` optional alongside; placed in `3dmodels/{Manufacturer}/` or `3dmodels/Misc/`; do not generate — attempt to download from manufacturer site, GrabCAD, or SnapEDA
- **3D model path in footprint**: `${KIPRJMOD}/../../3dmodels/{Manufacturer}/{PartNumber}.step`

## Category Files

| File | Contents |
|------|----------|
| `Custom_MCU.kicad_sym` | Microcontrollers and microprocessors |
| `Custom_Sensor.kicad_sym` | Temperature, humidity, IMU, etc. |
| `Custom_Connector.kicad_sym` | All connector types |
| `Custom_Passive.kicad_sym` | Resistors, capacitors, inductors (non-standard values/packages) |

Add new category files as needed when none of the above fit.

## Promotion Rule

When a manufacturer's parts in a category file reach 5, move them out into a dedicated `{Manufacturer}.kicad_sym` and rename the symbols to drop the manufacturer prefix.

## Adding a New Part

1. Decide: category file or manufacturer file? (use threshold rule above)
2. Symbol → add to the chosen `.kicad_sym`
3. Footprint → add `.kicad_mod` to the matching `.pretty` directory
4. 3D model → place `.step` in `3dmodels/{Manufacturer}/` or `3dmodels/Misc/`
5. Link 3D model path in the footprint properties
