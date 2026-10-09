════════════════════════════════════════════════════════════════════
AEQUIGEN-SS — BILL OF MATERIALS
Self-Starting Dual Rotor Axial Flux PM Generator
────────────────────────────────────────────────────────────────────
Version : 1.0 │ Date: 2026-06-12 │ Status: OPTIBEST BOM
Sheet: 1 of 2 │ Units: SI │ All tolerances: ±0.5mm unless noted
════════════════════════════════════════════════════════════════════


─── STRUCTURAL & HOUSING ──────────────────────────────────────────

┌─ ITEM │ QTY │ DESCRIPTION                     │ MATERIAL     │ EFE  ─┐
│  1    │  1  │ Front housing half               │ Al A356 rec. │ Tier3 │
│  2    │  1  │ Rear housing half                │ Al A356 rec. │ Tier3 │
│  3    │  1  │ Stator carrier ring              │ Al 6061 rec. │ Tier3 │
│  4    │  4  │ Housing tie bolts M6×80          │ SS 304 rec.  │ Tier3 │
│  5    │  4  │ Mounting feet                    │ Al 6061 rec. │ Tier3 │
│  6    │  1  │ Terminal box                     │ Al 6061 rec. │ Tier3 │
│  7    │  1  │ Lifting eye (M8 ring)            │ SS 304 rec.  │ Tier3 │
│  8    │  2  │ O-ring seal (housing) 325×5      │ EPDM         │ Tier2 │
│  9    │  1  │ O-ring seal (terminal box)       │ EPDM         │ Tier2 │
│ 10    │  4  │ M6×16 cap screw (term box)       │ SS 304 rec.  │ Tier3 │
└───────┴──────┴─────────────────────────────────┴──────────────┴──────┘


─── ROTOR SYSTEM ──────────────────────────────────────────────────

┌─ ITEM │ QTY │ DESCRIPTION                     │ MATERIAL     │ EFE  ─┐
│ 11    │  2  │ Rotor carrier disk (300×10mm)    │ Al 6061 rec. │ Tier3 │
│ 12    │ 64  │ Halbach segment — orientation A  │ Ferrite Y30  │ Tier2 │
│ 13    │ 64  │ Halbach segment — orientation B  │ Ferrite Y30  │ Tier2 │
│       │     │  (2 orientations × 64 = 128 total│              │       │
│       │     │   per rotor × 2 rotors = 256 seg)│              │       │
│ 14    │  1  │ Bio-epoxy potting (250 mL)       │ Hemp-oil     │ Tier1 │
│       │     │                                   │ bio-epoxy    │       │
│ 15    │ 16  │ Balance correction washers        │ Lead-free    │ Tier2 │
│ 16    │  2  │ Rotor key (6×6×30mm)             │ SS 304 rec.  │ Tier3 │
└───────┴──────┴─────────────────────────────────┴──────────────┴──────┘


─── STATOR SYSTEM ──────────────────────────────────────────────────

┌─ ITEM │ QTY │ DESCRIPTION                     │ MATERIAL     │ EFE  ─┐
│       │     │ OPTION A — PCB STATOR            │              │       │
│ 17a   │  1  │ PCB stator (300mm, 4-layer       │ FR4 + Cu    │ Tier3 │
│       │     │  6oz Cu, 48-slot, 3-phase)       │ 6oz/ft²     │       │
│ 17b   │  1  │ PCB ceramic stator (future)       │ Al₂O₃ + Cu  │ Tier2 │
│       │     │ OPTION B — LITZ WIRE STATOR       │              │       │
│ 18a   │  1  │ Winding jig (3D printed)          │ PLA/hemp    │ Tier1 │
│ 18b   │ 48  │ Coil — Litz (20×AWG24, 20 turns) │ Cu Litz     │ Tier3 │
│ 18c   │  1  │ Potting compound (100 mL)         │ Bio-epoxy   │ Tier1 │
│ 19    │  3  │ Output terminal (M8 stud)         │ Brass, Ni   │ Tier3 │
│ 20    │  3  │ Phase lead wire (1m × 4mm²)       │ Cu + silicone│ Tier3 │
│ 21    │ 48  │ Cable ties (coil retention)        │ PA66 rec.   │ Tier3 │
└───────┴──────┴─────────────────────────────────┴──────────────┴──────┘


─── GOVERNOR SYSTEM ────────────────────────────────────────────────

┌─ ITEM │ QTY │ DESCRIPTION                     │ MATERIAL     │ EFE  ─┐
│ 22    │  4  │ Governor flyweight               │ W-alloy      │ Tier2 │
│       │     │                                   │ (Pb-free)    │       │
│ 23    │  4  │ Flyweight pivot pin               │ SS 304 rec. │ Tier3 │
│ 24    │  4  │ Oil-less journal bearing (pivot)  │ Bronze+MoS₂ │ Tier2 │
│ 25    │  1  │ Governor sleeve (moves on shaft)  │ Al 6061 rec.│ Tier3 │
│ 26    │  1  │ Magnetic spring (repulsion ring)  │ NdFeB N42   │ Tier3*│
│ 27    │  1  │ Governor lever arm                 │ Al 6061 rec.│ Tier3 │
│ 28    │  2  │ Lever pivot pins                   │ SS 304 rec. │ Tier3 │
│ 29    │  2  │ Clevis pins + retainers            │ SS 304 rec. │ Tier3 │
│       │     │ * Transition — replace with CIL   │              │       │
│       │     │   diamond magnet when available    │              │       │
└───────┴──────┴─────────────────────────────────┴──────────────┴──────┘


─── BEARING & SHAFT ────────────────────────────────────────────────

┌─ ITEM │ QTY │ DESCRIPTION                     │ MATERIAL     │ EFE  ─┐
│ 30    │  2  │ Angular contact bearing 7205     │ Si₃N₄/steel │ Tier3 │
│ 31    │  1  │ Shaft (hollow, 25×18×300mm)      │ 17-4PH SS   │ Tier2 │
│ 32    │  2  │ Shaft snap ring (for bearings)    │ SS 301 rec. │ Tier3 │
│ 33    │  1  │ Shaft key (6×6×40mm)              │ SS 304 rec. │ Tier3 │
│ 34    │  1  │ Shaft seal (25×40×7mm)            │ NBR/FPM     │ Tier2 │
│ 35    │  2  │ Magnetic unloader rings           │ Ferrite     │ Tier2 │
└───────┴──────┴─────────────────────────────────┴──────────────┴──────┘


─── COOLING & THERMAL ──────────────────────────────────────────────

┌─ ITEM │ QTY │ DESCRIPTION                     │ MATERIAL     │ EFE  ─┐
│ 36    │  1  │ Thermal pad (stator→housing) 0.5mm│ BN-filled   │ Tier2 │
│       │     │                                   │ silicone     │       │
│ 37    │  1  │ Cooling fin set (10mm H × 5mm P)  │ Al 6063 rec.│ Tier3 │
└───────┴──────┴─────────────────────────────────┴──────────────┴──────┘


─── FASTENERS & MISCELLANEOUS ──────────────────────────────────────

┌─ ITEM │ QTY │ DESCRIPTION                     │ MATERIAL     │ EFE  ─┐
│ 38    │ 12  │ M4×12 SHCS (stator→carrier)      │ SS 304 rec. │ Tier3 │
│ 39    │ 8   │ M5×16 SHCS (rotor→carrier)        │ SS 304 rec. │ Tier3 │
│ 40    │ 4   │ M8×25 SHCS (feet→housing)         │ SS 304 rec. │ Tier3 │
│ 41    │ 4   │ M6 nut (tie bolts)                │ SS 304 rec. │ Tier3 │
│ 42    │ 16  │ M4 flat washer                    │ SS 304 rec. │ Tier3 │
│ 43    │ 1   │ Desiccant pack (terminal box)      │ Silica gel  │ Tier2 │
│ 44    │ 1   │ Vent plug (G¼ with membrane)       │ Al + PTFE   │ Tier2 │
└───────┴──────┴─────────────────────────────────┴──────────────┴──────┘


─── SUMMARY ────────────────────────────────────────────────────────

  Total distinct items   : 44
  Total parts count      : ~380 (including fasteners)
  Total material cost    : $120-150 USD (present sustainable)
  Recyclable mass fraction: >95%
  Rare earth content     : <1 g (governor spring only, transitional)
  Items with CIL upgrade  : 44/44 (100% pathway defined)


════════════════════════════════════════════════════════════════════
                      END OF BILL OF MATERIALS
               AEQUIGEN-SS │ v1.0 │ OPTIBEST BOM
════════════════════════════════════════════════════════════════════
