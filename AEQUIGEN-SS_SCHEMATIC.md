════════════════════════════════════════════════════════════════════
AEQUIGEN-SS — SCHEMATIC DIAGRAMS
Self-Starting Dual Rotor Axial Flux PM Generator
────────────────────────────────────────────────────────────────────
Version : 1.0 │ Date: 2026-06-12 │ Status: OPTIBEST SCHEMATIC
════════════════════════════════════════════════════════════════════


─── 1. SYSTEM BLOCK DIAGRAM ───────────────────────────────────────

    ┌─────────────────────────────────────────────────────────────┐
    │                 AEQUIGEN-SS SYSTEM OVERVIEW                  │
    └─────────────────────────────────────────────────────────────┘

                           ┌──────────────┐
                           │  PRIME MOVER  │
                           │ (Wind/Water/  │
                           │  Muscle/PTO)  │
                           └──────┬───────┘
                                  │
                                  │ Mechanical rotation
                                  │ (120-600 RPM)
                                  ▼
              ┌──────────────────────────────────────────────┐
              │              AEQUIGEN-SS GENERATOR            │
              │                                               │
              │  ┌──────┐   ┌────────┐   ┌──────┐             │
              │  │Rotor ├───┤ Stator ├───┤Rotor │             │
              │  │  1   │   │(core-  │   │  2   │             │
              │  │Halbach│   │ less)  │   │Halbach│             │
              │  └───┬───┘   └───┬────┘   └───┬───┘             │
              │      │           │            │                 │
              │      └───────────┼────────────┘                 │
              │                  │                              │
              │          ┌───────▼────────┐                     │
              │          │   Governor     │                     │
              │          │ (centrifugal)  │                     │
              │          │ regulates gap  │                     │
              │          └───────────────┘                     │
              └──────────────────────────────────────────────┘
                                  │
                    ┌─────────────┴─────────────┐
                    │           3-phase AC       │
                    ▼                            ▼
          ┌─────────────────┐         ┌─────────────────┐
          │  AC Load (direct)│         │  Rectifier + DC  │
          │  (heaters, lamps,│         │  (battery,       │
          │   AC motors)     │         │   electronics)   │
          └─────────────────┘         └─────────────────┘


─── 2. ELECTRICAL SCHEMATIC ───────────────────────────────────────

                     ┌─────────────────────┐
                     │  AEQUIGEN-SS STATOR  │
                     │  3-PHASE WYE (STAR) │
                     └─────────────────────┘

           Phase A ──────┬───────┬───────┬───────┬──· · ·──┐
                         │       │       │       │         │
                        ┌┴┐     ┌┴┐     ┌┴┐     ┌┴┐       │
                        │ │     │ │     │ │     │ │       │
                        └┬┘     └┬┘     └┬┘     └┬┘       │
                         │       │       │       │         │
                         └───┬───┴───┬───┴───┬───┘         │
                             │       │       │             │
           Phase B ──────┬───┼───────┼───────┼───────· · ·─┤
                         │   │       │       │             │
                        ┌┴┐ ┌┴┐     ┌┴┐     ┌┴┐           │
                        │ │ │ │     │ │     │ │           │
                        └┬┘ └┬┘     └┬┘     └┬┘           │
                         │   │       │       │             │
                         └───┼───┬───┴───┬───┘             │
                             │   │       │                 │
           Phase C ──────┬───┼───┼───────┼──────────· · ·──┤
                         │   │   │       │                 │
                        ┌┴┐ ┌┴┐ ┌┴┐     ┌┴┐               │
                        │ │ │ │ │ │     │ │               │
                        └┬┘ └┬┘ └┬┘     └┬┘               │
                         │   │   │       │                 │
                         └───┴───┴───┬───┘                 │
                                     │                     │
                                    ┌┴┐                    │
                                    │ │ (Neutral, not      │
                                    └┬┘  connected externally)
                                     │
                                   NEUTRAL POINT


─── 3. HALBACH ARRAY LAYOUT (ROTOR 1, VIEWED FROM STATOR) ────────

                     ┌─────────────────────────────┐
                     │  ROTOR 1 — HALBACH PATTERN   │
                     │  16 POLE, 64 SEGMENTS        │
                     │  (CCW = Direction of rotation)│
                     └─────────────────────────────┘

                          ╔══╗    ╔══╗
                      ╔══╗    ╔══╗    ╔══╗
                  ╔══╗    ╔══╗    ╔══╗    ╔══╗
              ╔══╗    ╔══╗    ╔══╗    ╔══╗    ╔══╗
              ║N ║    ║→ ║    ║S ║    ║← ║    ║N ║
              ╚══╝    ╚══╝    ╚══╝    ╚══╝    ╚══╝
                  ╚══╝    ╚══╝    ╚══╝    ╚══╝
                      ╚══╝    ╚══╝    ╚══╝
                          ╚══╝    ╚══╝

  LEGEND:  ╔══╗ Ferrite segment
           ║N ║ North pole (flux INTO stator)
           ║S ║ South pole (flux OUT of stator)
           ║→ ║ Horizontal flux segment (Halbach)
           ║← ║ Horizontal flux segment (Halbach reverse)

  Each pole (22.5° mechanical) = 4 segments × 2 radial rows
  16 poles × 4 segments = 64 total per rotor

  Rotor 2: Mirror image, aligned NS-NS with Rotor 1


─── 4. GOVERNOR MECHANISM SCHEMATIC ───────────────────────────────

                ┌─────────────────────────────────────┐
                │  GOVERNOR CROSS-SECTION (AT SPEED)  │
                └─────────────────────────────────────┘

            ┌─────────────────────────────────┐
            │  FLYW-1    FLYW-2                │
            │    ╲      ╱                      │
            │     ╲    ╱                       │
            │   ╱╲    ╱╱╲    ╱╲               │
            │  ╱  ╲  ╱  ╲  ╱  ╲              │
            │ ╱   │ ╱   │ ╱   │               │
            │     │     │     │                │
            │ SLEEVE ────► AXIAL DISPLACEMENT   │
            │     │     │     │                │
            │     ▼     ▼     ▼                │
            │  ╔═══════════════════╗            │
            │  ║  MAGNETIC SPRING  ║  (repels)  │
            │  ╚═══════════════════╝            │
            │         │     │                    │
            │         ▼     ▼                    │
            │      ┌───────────┐                 │
            │      │ ROTOR 2   │◄── Axial motion │
            │      │ (splined) │    adjusts gap   │
            │      └───────────┘                 │
            └─────────────────────────────────┘

  OPERATION:
  1. Speed increases → flyweights swing outward (centrifugal force)
  2. Flyweights pull sleeve toward shaft end
  3. Sleeve pulls lever → lever moves Rotor 2 axially
  4. Rotor 2 gap increases → flux linkage decreases → voltage drops
  5. Equilibrium: centrifugal force = magnetic spring force
  6. Speed decreases → spring returns Rotor 2 → gap closes → voltage rises


─── 5. WINDING CONFIGURATION (SINGLE COIL DETAIL) ─────────────────

                               ┌─────┐
                    ┌──────────┤COIL ├──────────┐
                    │          │  #N  │          │
                    │          └─────┘          │
                    │                           │
               ┌────┴────┐               ┌────┴────┐
               │  LAYER 1 │               │  LAYER 2 │
               │ (forward)│               │ (return) │
               └────┬────┘               └────┬────┘
                    │                         │
                    └────────────┬────────────┘
                                 │
                              ┌──┴──┐
                              │ VIA │ (through PCB or
                              └─────┘  twisted in Litz)

  PCB: Rectangular spiral, 20 turns, 2 layers per coil side
  Litz: 20 turns of 20×AWG24 bundle, wave-wound in jig

  Coil dimensions: 25 mm radial × 15 mm tangential
  Each phase: 16 coils in series (distributed around stator)


─── 6. AXIAL CROSS-SECTION ─────────────────────────────────────────

  (Section view through centerline)

  ┌────────────────────────────────────────────────────────────┐
  │                  AEQUIGEN-SS — SECTION A-A                  │
  │  (Not to scale — axial dimension exaggerated for clarity)   │
  └────────────────────────────────────────────────────────────┘

            ┌─── Rotor 1 (fixed) ──┐
            │   ← ferrite Halbach →│
            │                      │
  ──────────┤ │← 3mm air gap →│   │──────────
            │                    │ │
            │  ← stator coreless─│ │
            │                    │ │
  ──────────┤   │← 3mm air gap →│ │──────────
            │                    ▼ │
            │  Rotor 2 (splined,  │
            │  axially movable)   │
            │   ← ferrite Halbach→│
            │                     │
            └─────────────────────┘

  ┌───── Housing ───┐   ┌─── Housing ─────┐
  │   Bearing 1      │   │   Bearing 2     │
  │   ← Shaft →      │   │   ← Shaft →     │
  │   Seal           │   │   (to governor)  │
  └──────────────────┘   └─────────────────┘

  AXIAL DIMENSIONS:
    Housing front thickness:  5 mm
    Rotor 1 thickness:       15 mm
    Air gap 1:                3 mm
    Stator thickness:         4 mm
    Air gap 2:                3 mm
    Rotor 2 thickness:       15 mm
    Governor mechanism:      15 mm
    Housing rear thickness:   5 mm
    Bearings + shaft ext:    15 mm
    ─────────────────────────────
    TOTAL:                  80 mm


════════════════════════════════════════════════════════════════════
                    END OF SCHEMATIC DIAGRAMS
               AEQUIGEN-SS │ v1.0 │ OPTIBEST SCHEMATIC
════════════════════════════════════════════════════════════════════
