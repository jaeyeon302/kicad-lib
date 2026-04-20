# KiCad Library Plan — LV VFD MCB Interface Connectors
Date: 2026-04-19
Source: [HDKSOE] LV VFD MCB 인터페이스_260213.pdf

---

## Connector Part List (extracted from "Con Model" column)

| # | Con Model | Manufacturer | Pins | Used at (Con No.) | Interface |
|---|-----------|-------------|------|-------------------|-----------|
| 1 | 231-533 | Phoenix Contact | 3 | J53 | Control power |
| 2 | 231-534 | Phoenix Contact | 4 | J18~J29, J31,J33,J35, J37,J38, J48,J50, J34 | AI, NTC, Spare AI/AO, CT/PT power |
| 3 | 231-538 | Phoenix Contact | 8 | J10, J14, J8 | DI, DO, Encoder |
| 4 | 232-364 | Phoenix Contact | 4 | J24~J29, J30,J32,J36 | AI (grid side) |
| 5 | 232-368 | Phoenix Contact | 8 | J11, J15 | DI (CB state), DO (CB command) |
| 6 | HIF3BA-30PA-2.54DSA | Hirose | 30 | CN1 (×2) | MSC/GSC PWM gate signals |
| 7 | MJ-657PW-8-BK | (TBD) | 8 | J1, J3, J7 | RS485 (PLC, HMI, Spare) |
| 8 | 8498010210A | Molex | - | J52 | Ethernet (Spare) |
| 9 | 6368011-3 | TE Connectivity | 8 | J2, J4 | CAN (Spare, MCB–PEBD) |

---

## TODO

### Phase 1 — Confirm part list
- [x] User confirms the connector part list above

### Phase 2 — Datasheet download (per part)
- [x] 231-533 → download to `docs/datasheet/Phoenix_Contact/`
- [x] 231-534 → download to `docs/datasheet/Phoenix_Contact/`
- [x] 231-538 → download to `docs/datasheet/Phoenix_Contact/`
- [x] 232-364 → download to `docs/datasheet/Phoenix_Contact/`
- [x] 232-368 → download to `docs/datasheet/Phoenix_Contact/`
- [x] HIF3BA-30PA-2.54DSA → download to `docs/datasheet/Hirose/`
- [x] MJ-657PW-8-BK → identify manufacturer, download to `docs/datasheet/{Manufacturer}/`
- [x] 8498010210A → download to `docs/datasheet/Molex/`
- [x] 6368011-3 → download to `docs/datasheet/TE_Connectivity/`

### Phase 3 — Symbol creation (strictly follow datasheet)
- [x] 231-533 — symbol in `Custom_Connector.kicad_sym`
- [x] 231-534 — symbol
- [x] 231-538 — symbol
- [x] 232-364 — symbol
- [x] 232-368 — symbol
- [x] HIF3BA-30PA-2.54DSA — symbol (30-pin, may warrant Phoenix_Contact file if grouped)
- [x] MJ-657PW-8-BK — symbol
- [x] 8498010210A — symbol
- [x] 6368011-3 — symbol

### Phase 4 — Footprint creation (strictly follow datasheet land pattern)
- [x] 231-533 — footprint in `Custom_Connector.pretty/`
- [x] 231-534 — footprint
- [x] 231-538 — footprint
- [x] 232-364 — footprint
- [x] 232-368 — footprint
- [x] HIF3BA-30PA-2.54DSA — footprint
- [x] MJ-657PW-8-BK — footprint
- [x] 8498010210A — footprint
- [x] 6368011-3 — footprint

### Phase 5 — 3D model (download if available)
- [x] Search and download `.step` for each part; place in `3dmodels/{Manufacturer}/`
