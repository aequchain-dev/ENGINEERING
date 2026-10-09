════════════════════════════════════════════════════════════════════
AEQUIGEN-SS — MANUFACTURING GUIDE
Self-Starting Dual Rotor Axial Flux PM Generator
────────────────────────────────────────────────────────────────────
Version : 1.0 │ Date: 2026-06-12 │ Status: OPTIBEST PROCEDURE
Intended for: Local machine shops, regional manufacturing hubs
════════════════════════════════════════════════════════════════════


─── TABLE OF CONTENTS ──────────────────────────────────────────────

    1. Safety & Prerequisites
    2. Tools & Equipment Required
    3. Rotor Fabrication
    4. Stator Fabrication (Option A: PCB)
    5. Stator Fabrication (Option B: Litz Wire)
    6. Housing Fabrication
    7. Shaft & Bearing Preparation
    8. Governor Fabrication
    9. Final Assembly Sequence
    10. Quality Control Checkpoints
    11. Testing & Commissioning
    12. CIL Diamond Migration Notes


─── 1. SAFETY & PREREQUISITES ──────────────────────────────────────

⚠ WARNING:
  • Ferrite magnets are brittle — handle with care, wear eye protection
  • Strong magnetic fields — keep pacemakers, credit cards, electronics
    at safe distance (>500 mm)
  • Magnet handling: use non-magnetic tools (brass, stainless), always
    use fixtures to prevent pinch injuries
  • Bio-epoxy: work in ventilated area, use nitrile gloves
  • Rotating machinery: ensure lockout/tagout before assembly

Prerequisites:
  • Read master design document (AEQUIGEN-SS_MASTER.md) completely
  • All materials per BOM (AEQUIGEN-SS_BOM.md) — verify received
  • Workspace: Clean, non-magnetic workbench, 1.2m × 0.8m minimum
  • Skills: General machining, soldering, basic electrical measurement


─── 2. TOOLS & EQUIPMENT REQUIRED ─────────────────────────────────

MANDATORY (Minimum Workshop):
  ┌─ TOOL                              │ USE                            ┐
  │ Manual lathe (300 mm swing, 500 mm  │ Rotor carriers, shaft          │
  │   between centers)                  │                                │
  │ Manual mill (400 × 300 mm travel)   │ Housing, pocket cutting        │
  │ Drill press + drill bits (1-13 mm)  │ Bolt holes, bearing seats     │
  │ Tap set (M4, M5, M6, M8)           │ Threaded holes                 │
  │ Soldering station (60W+)            │ Phase connections              │
  │ Multimeter (True RMS, 600V CAT III) │ Electrical test                │
  │ Gauss meter (0-1 T)                 │ Magnet flux verification       │
  │ Magnet handling fixture              │ Safe magnet insertion         │
  │ Dynamic balancer (or V-block +      │ Rotor balancing               │
  │   accelerometer method)             │                                │
  └─────────────────────────────────────┴────────────────────────────────┘

RECOMMENDED (Regional Hub):
  ┌─ TOOL                              │ USE                            ┐
  │ CNC mill                            │ Production rotor pockets       │
  │ EDM or waterjet                     │ Precision Halbach pockets     │
  │ Dynamic balancing machine           │ Precision balance (G2.5)       │
  │ Vacuum potting chamber               │ Void-free epoxy potting       │
  │ 3D printer (300 × 300 mm)           │ Litz winding jig (Option B)   │
  │ Insulation resistance tester (500V)  │ Hi-pot test                    │
  │ Thermal camera                       │ Thermal validation            │
  └─────────────────────────────────────┴────────────────────────────────┘


─── 3. ROTOR FABRICATION ──────────────────────────────────────────

3.1 Machine Rotor Carriers (×2)

  STEP 1: Face both sides flat and parallel (<0.05 mm TIR)
  STEP 2: Turn outer diameter to 298.0 mm (leaves 1 mm for final
          cleanup after potting)
  STEP 3: Bore center hole to 25.05 mm (slip fit on shaft)
  STEP 4: Cut keyway (6 mm × 3.5 mm deep) using broach or slotter
  STEP 5: If using CNC/EDM: Cut Halbach pockets per pattern in
          schematic. Pocket depth: 8.2 mm (for 8 mm magnets + 0.2 mm
          clearance). Pocket width: 6.5 mm (for 6 mm segments)
  STEP 6: If manual: Use dividing head, drill/mill rectangular
          pockets to depth. 64 pockets per rotor.

3.2 Insert Magnets

  ⚠ CRITICAL: Magnetization orientation MUST match Halbach diagram.
    Use orientation fixture (brass template with direction markings).

  STEP 7: Place rotor carrier in non-magnetic fixture
  STEP 8: Insert each ferrite segment with correct orientation
          (14 segments per pole pair × 4 pole pairs per rotor)
  STEP 9: Verify orientation with Gauss meter after each pole group
  STEP 10: Ensure all segments are flush (±0.1 mm)

3.3 Potting

  STEP 11: Mix bio-epoxy per manufacturer spec (typically 1:1 ratio)
  STEP 12: Apply vacuum (if available) to de-air epoxy
  STEP 13: Pour epoxy to fill all gaps between segments, ensure
           no air pockets
  STEP 14: Cure at room temperature 24 h, or 60°C for 4 h

3.4 Final Machining & Balance

  STEP 15: After cure, face off rotor surface to expose magnets
           (remove ~0.5 mm), final thickness: 15.0 ± 0.1 mm
  STEP 16: Turn OD to 300.0 mm (final dimension)
  STEP 17: Measure axial runout — must be <0.05 mm
  STEP 18: Dynamic balance to G2.5 per ISO 1940:
           Permissible residual unbalance: U = 2.5 × m × Ω / 1000
           At 375 RPM: ~0.06 g·mm per rotor
  STEP 19: Correct imbalance by drilling (6 mm max depth) in
           non-magnet areas, 2-4 mm from edge

QA Checkpoint 1: Rotor Verification
  ☐ All 64 magnets present and secure
  ☐ Magnet orientation verified per Halbach pattern
  ☐ Final thickness: 15.0 ± 0.1 mm
  ☐ Axial runout: <0.05 mm
  ☐ Dynamic balance: G2.5 or better
  ☐ No cracks in ferrite segments


─── 4. STATOR FABRICATION (OPTION A — PCB) ────────────────────────

For high-volume production. Requires PCB fabrication capability.

  STEP 1: Order PCB per specification:
          • Diameter: 300 mm (panelized or single)
          • Layers: 4 (2 signal, 2 ground/thermal)
          • Copper weight: 6 oz/ft² (210 µm)
          • Minimum trace width/spacing: 0.5 mm / 0.5 mm
          • Material: FR4 (present) or ceramic (transition)
          • Finish: ENIG (immersion gold)
          • Solder mask: Both sides, green
  STEP 2: Upon receipt: visual inspection, continuity check
  STEP 3: Solder phase interconnect jumpers (per schematic)
  STEP 4: Solder output leads (4 mm² wire, 200 mm length)
  STEP 5: Apply bio-epoxy conformal coating (dip or spray)
  STEP 6: Insulation resistance test: >100 MΩ at 500 V

QA Checkpoint 2a: PCB Stator Verification
  ☐ All 48 coils continuous, no opens
  ☐ No shorts between phases
  ☐ Phase resistance within ±5% of 0.35 Ω
  ☐ Insulation resistance >100 MΩ at 500 VDC
  ☐ Visual: no lifted traces, no solder bridges
  ☐ Flatness: <0.3 mm over entire surface


─── 5. STATOR FABRICATION (OPTION B — LITZ WIRE) ──────────────────

For local manufacturing without PCB capability. Requires 3D printer
or manual jig fabrication.

  STEP 1: 3D-print winding jig (hemp/PLA or flax/bio-epoxy filament)
  STEP 2: Wind each coil (48 total):
          • Litz wire: 20 strands AWG 24 (0.51 mm each)
          • 20 turns per coil
          • Wind direction alternating per phase (per schematic)
          • Leave 100 mm lead ends for interconnection
  STEP 3: Fix wound coils in jig with epoxy drops (temporary)
  STEP 4: Interconnect coils per phase (series):
          • Phase A: Coils 1, 4, 7, 10, 13, 16, 19, 22, 25, 28,
            31, 34, 37, 40, 43, 46
          • Phase B: Coils 2, 5, 8, 11, 14, 17, 20, 23, 26, 29,
            32, 35, 38, 41, 44, 47
          • Phase C: Coils 3, 6, 9, 12, 15, 18, 21, 24, 27, 30,
            33, 36, 39, 42, 45, 48
  STEP 5: Solder interconnects, insulate with heat shrink
  STEP 6: Pot entire stator assembly with bio-epoxy in jig
  STEP 7: Cure 24 h at room temperature or 4 h at 60°C
  STEP 8: Remove from jig, trim flash

QA Checkpoint 2b: Litz Stator Verification
  ☐ All 48 coils wound, resistance verified per spec
  ☐ Phase resistance 0.28 ± 0.02 Ω (at 20°C)
  ☐ No shorts between phases
  ☐ Insulation resistance >100 MΩ at 500 VDC
  ☐ Potting complete — no voids, no exposed conductors
  ☐ Flatness: <0.5 mm


─── 6. HOUSING FABRICATION ────────────────────────────────────────

  STEP 1: Cast (sand) or machine housing halves from recycled
          aluminum A356 or 6061
  STEP 2: Machine bearing seats (per bearing spec: 25 mm bore,
          tolerance H7)
  STEP 3: Machine seal groove (for shaft seal, per NBR spec)
  STEP 4: Machine stator carrier ring location (register fit)
  STEP 5: Drill and tap mounting holes per BOM
  STEP 6: Machine cooling fins (10 mm height, 5 mm pitch) on
          outer diameter
  STEP 7: Anodize (present) or DLC coat (transition) for corrosion
          protection
  STEP 8: Install O-ring seals in grooves

QA Checkpoint 3: Housing Verification
  ☐ Bearing bore: 25 mm H7 (+0.021 / -0)
  ☐ Seal bore: 25 mm H8 (+0.033 / -0)
  ☐ Stator register concentric to bearing bore: <0.05 mm TIR
  ☐ Housing faces parallel: <0.1 mm
  ☐ No casting porosity exposing interior


─── 7. SHAFT & BEARING PREPARATION ────────────────────────────────

  STEP 1: Machine shaft from 17-4 PH stainless (or 304 recycled):
          • Overall length: 300 mm
          • Bearing journals: 25 mm h6 (-0.006 / -0.015)
          • Rotor shoulders: 25 mm for rotors
          • Keyway: 6 mm × 4 mm depth, broached
          • Spline section for Rotor 2: 18 mm, 24-tooth involute
            (allows 10 mm axial travel)
          • Hollow bore: 18 mm through
  STEP 2: Install bearings on shaft (heat bearings to 100°C,
          shaft at room temperature — slip fit)
  STEP 3: Install magnetic unloader rings on shaft between bearings
          and rotor locations
  STEP 4: Snap ring installation
  STEP 5: Install shaft seal in housing (not on shaft — install
          during final assembly)

QA Checkpoint 4: Shaft Verification
  ☐ Bearing journals: 25.000 ± 0.006 mm
  ☐ Rotor seats: concentric to bearings <0.03 mm TIR
  ☐ Keyway centered on rotor seat
  ☐ Spline section: axial travel 10 mm minimum
  ☐ Shaft straightness: <0.05 mm over 300 mm


─── 8. GOVERNOR FABRICATION ──────────────────────────────────────

  STEP 1: Machine flyweights (×4) from Pb-free W-alloy
          • Mass per flyweight: 50.0 ± 0.1 g
          • Profile: crescent shape (6 mm × 20 mm × 30 mm)
          • Pivot hole: 3.0 mm reamed
  STEP 2: Machine governor sleeve from Al 6061
          • Slides on shaft (25 mm bore with 0.1 mm clearance)
          • Contains lever cam slots (2 slots, opposite sides)
          • Pivot pin holes reamed 3.0 mm
  STEP 3: Install oil-less journal bearings in flyweights
          (press fit)
  STEP 4: Assemble magnetic spring:
          • Two concentric NdFeB rings (ironless — magnetic repulsion)
          • Ring 1 (inner, fixed to shaft): 25 mm ID × 35 mm OD × 5 mm
          • Ring 2 (outer, fixed to sleeve): 36 mm ID × 46 mm OD × 5 mm
          • Air gap between rings: 1 mm radial
          → Creates axial repulsion force: 15-25 N (adjust by thickness)
  STEP 5: Assemble lever mechanism (links sleeve to Rotor 2)
  STEP 6: Verify free movement of all pivot joints

QA Checkpoint 5: Governor Verification
  ☐ Each flyweight mass: 50.0 ± 0.1 g
  ☐ Governor sleeve slides freely on shaft (>50 mm travel)
  ☐ Magnetic spring provides 15-25 N axial force
  ☐ All pivots free-moving (no binding)
  ☐ Lever mechanism connects sleeve to Rotor 2 correctly


─── 9. FINAL ASSEMBLY SEQUENCE ────────────────────────────────────

  ┌─ STEP │ ACTION                                               ─┐
  │   1   │ Install shaft seal in rear housing (press in)         │
  │   2   │ Insert shaft through rear housing bearing             │
  │   3   │ Position rear housing on stand (vertical, open up)   │
  │   4   │ Slide Rotor 2 onto shaft spline (keyed, axially      │
  │       │   free)                                               │
  │   5   │ Install stator assembly on stator carrier ring        │
  │       │   (bolt M4×12, 12 places)                             │
  │   6   │ Run phase leads through housing to terminal box       │
  │   7   │ Slide Rotor 1 onto shaft (keyed, fixed position)      │
  │       │   Secure with key and shaft collar                    │
  │   8   │ Connect governor lever to Rotor 2                     │
  │   9   │ Slide governor sleeve onto shaft                      │
  │  10   │ Install magnetic spring rings                         │
  │  11   │ Attach flyweights to sleeve (pivot pins + retainers)  │
  │  12   │ Place front housing (align O-ring, bolt holes)        │
  │  13   │ Insert tie bolts (M6×80, 4 places) — torque 8 N·m    │
  │  14   │ Install front bearing (if separate)                   │
  │  15   │ Install mounting feet (M8×25, 4 places)              │
  │  16   │ Install terminal box with gasket                      │
  │  17   │ Connect phase leads to terminals (phase-to-terminal   │
  │       │   mapping per electrical schematic)                   │
  │  18   │ Install desiccant pack + vent plug                    │
  │  19   │ Rotate shaft by hand — verify free rotation           │
  │       │   (no scraping, no binding)                           │
  │  20   │ Final torque check on all fasteners                   │
  └───────┴───────────────────────────────────────────────────────┘


─── 10. QUALITY CONTROL CHECKPOINTS ───────────────────────────────

  Throughout assembly, verify:

  ☐ All fasteners torqued to spec (M4: 3 N·m, M5: 6 N·m, M6: 8 N·m,
    M8: 20 N·m)
  ☐ All threadlocker applied (blue Loctite or equivalent bio variant)
  ☐ O-rings seated, not pinched
  ☐ Gaskets installed, sealing surfaces clean
  ☐ Phase leads not pinched between housing halves
  ☐ Rotor-to-stator clearance equal all around
  ☐ Hand-rotate: smooth, no rubbing, no scraping
  ☐ All fasteners present per BOM


─── 11. TESTING & COMMISSIONING ───────────────────────────────────

── 11.1 BENCH TESTS (Every Unit) ──

  TEST 1 — Continuity & Insulation:
    ☐ Phase A resistance: 0.35 ± 0.02 Ω (PCB) / 0.28 ± 0.02 Ω (Litz)
    ☐ Phase B resistance: same
    ☐ Phase C resistance: same
    ☐ Phase-to-phase: no short
    ☐ Phase-to-ground: >100 MΩ at 500 VDC

  TEST 2 — No-Load Run:
    ☐ Drive shaft at 375 RPM (via variable-speed drill or lathe)
    ☐ Measure frequency: 50 ± 1 Hz
    ☐ Measure line voltage (no load): 56 ± 3 VAC
    ☐ Measure phase voltage (no load): 32 ± 2 VAC
    ☐ Listen for abnormal noise: <55 dB(A) at 1 m
    ☐ Feel for vibration: <2 mm/s RMS

  TEST 3 — Governor Sweep:
    ☐ 120 RPM: frequency > 45 Hz, voltage > 40 VAC
    ☐ 375 RPM: frequency 50 ± 1 Hz, voltage 56 ± 3 VAC
    ☐ 600 RPM: frequency < 55 Hz, voltage < 72 VAC
    ☐ Governor responds within 2 seconds to speed change

  TEST 4 — Load Test:
    ☐ Connect 3-phase resistive load (48 V, 12 A per phase)
    ☐ Run at 375 RPM for 30 minutes
    ☐ Voltage at load: 48 ± 5 VAC
    ☐ Current: 12 ± 1 A per phase
    ☐ Power: 1,000 ± 50 W
    ☐ Temperature (external housing): <70°C
    ☐ Temperature (internal, estimate): <80°C

── 11.2 TYPE TESTS (Design Validation, First Article) ──

  TEST 5 — Efficiency Map:
    Measure at 25%, 50%, 75%, 100%, 125% load:
    ☐ 25%: ≥96% efficiency
    ☐ 50%: ≥96% efficiency
    ☐ 75%: ≥95.5% efficiency
    ☐ 100%: ≥95% efficiency
    ☐ 125%: ≥93% efficiency

  TEST 6 — Thermal:
    ☐ Thermal imaging at 60 min rated load: max temp <80°C
    ☐ No hot spots >10°C above average

  TEST 7 — Over-Speed:
    ☐ Run at 1,200 RPM for 2 minutes
    ☐ No mechanical damage, no permanent deformation
    ☐ Post-test vibration unchanged (<2 mm/s)

  TEST 8 — Short Circuit:
    ☐ 3-phase bolted short at rated speed for 10 seconds
    ☐ No damage to windings, no magnet demagnetization
    ☐ Post-test no-load voltage within 2% of pre-test


─── 12. CIL DIAMOND MIGRATION NOTES ──────────────────────────────

When CIL diamond materials become available (per AEQUCHAIN Phase 2+):

  • Rotor carrier: Replace Al with CIL diamond composite.
    Machining requires diamond tooling; or use near-net-shape CVD.
    Mass reduction: 1.8 kg → 0.4 kg per rotor.

  • Permanent magnets: Replace ferrite with CIL diamond PM.
    Br increases from 0.42T to ~1.5T — permits 50% diameter
    reduction or 3× power increase in same form factor.
    NOTE: Higher flux requires thicker stator winding to avoid
    saturation — redesign winding for 12 turns instead of 20.

  • Stator conductor: Replace copper with CIL diamond conductor.
    Resistivity ~50% of copper (lower), allows higher current
    density or thinner stator. Thermal conductivity of diamond
    (2,200 W/m·K) provides integral heat spreading — no separate
    thermal pad needed.

  • Housing: Replace Al with CIL diamond composite.
    Mass reduction: 3.2 kg → 0.6 kg. Integral thermal management
    (entire housing acts as heat sink).

  • Bearings: Replace hybrid ceramic with full CIL diamond.
    Zero wear, infinite life in clean environment, no lubrication.

  • Shaft: Replace 17-4PH with CIL diamond composite.
    Mass reduction, higher stiffness, zero corrosion.

  • Governor spring: Replace NdFeB with CIL diamond PM.
    Eliminates the <1 g rare earth content. Magnetic repulsion
    force unchanged (scales with remanence).

  • Estimated upgraded mass: 9.8 kg → 3.2 kg (67% reduction)
  • Estimated efficiency gain: 95% → 97% (lower I²R with diamond
    conductor, zero bearing friction with diamond bearings)
  • Manufacturing: Requires CIL diamond fabrication capability —
    CVD or SPS near-net-shape. Not yet available at scale.


════════════════════════════════════════════════════════════════════
                    END OF MANUFACTURING GUIDE
               AEQUIGEN-SS │ v1.0 │ OPTIBEST PROCEDURE
════════════════════════════════════════════════════════════════════
