# AEQUBIN v1.0 — SCHEMATIC (dimensional & interface chain)

| field | value |
|---|---|
| document ID | AEQUBIN-SCHEMATIC-100 |
| status | **[SPEC]** — dimensions engine-generated (`python -m engine.cli geometry`) |
| truth | `engine/geometry.py` — single source of geometry truth |

## 1. AEQUCRATE-400 — v1.1 HASH-RAIL lattice (Rubik-class)

```
            TOP (female # grooves, depth 4.0)         SIDE (half-lap #)
   ┌───────────────────────────────┐    ┌───────────────────────────┐
   │   ═══════════════════════════ │    │ ─────┬─────────┬────────── │  rails proud 2.0 /
   │   ═══        ═════════   ═══  │    │      │  bridge ◉│          │  channels recessed 2.0
   │  grooves 8 wide, crossing     │    │ ─────┴─────────┴────────── │  (envelope = mid-plane
   │  detent pockets at crossings  │    │      │  (hinge 0.4)       │   => pitch EXACT 400×300)
   └───────────────────────────────┘    └───────────────────────────┘

            BOTTOM (male # ribs 4.0 × 8.0)         CROSSING (section)
   ┌───────────────────────────────┐    ─┬─ ← bearing pad 40×40 (carries column)
   │   ▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬ │    ─┼─ ← bridge 24×10 on 0.4 living hinge
   │   ▬▬        ▬▬▬▬▬▬▬▬   ▬▬▬   │    ─┴─   snaps 1.2 mm detent = LOCK
   │   ribs drop into grooves      │
   └───────────────────────────────┘    flag [12×6×2]: pins bridge flat = SLIDE
```

- **Lattice behavior (Rubik-like):** any crate slides into an adjacent empty
  row/column cell — in-row via half-lap side rails (slide any direction),
  in-stack via the vertical groove cross (2-DOF). Flag raised = SLIDE
  (semi-locked); flag lowered = bridge snaps into the 1.2 mm detent = LOCK.
  Separation is always a guided slide back along the rail axis.
- **v1.2 CLIMB + per-position lock (G9, user-found gap fix):** all **12 edges
  are full-length half-lap tracks** — a column forms 4 continuous vertical
  ladder tracks, a row forms horizontal tracks. A crate's edge channels
  straddle 2 tracks: hook on, **slide UP/DOWN the column ladder or ALONG a
  row**, and the **per-pitch detent locks it at EVERY crate position**
  (vertical pitch 310 mm, horizontal 400/300 mm). Static hold FOS 20.2
  (loaded, engine); snatch loads → T9.
- **Load-path separation (G8):** the 40×40 mm crossing **bearing pads** carry
  the column (FOS 30.6 at 4 pads, 15.3 conservative 2-pad); the 0.4 mm
  living-hinge **bridges latch only** and never carry.
- **Uplift:** a side-engaged pair resists 14,080 N (root-tear governing,
  lip capture stronger) → **FOS 17.6** vs a 800 N two-person lift.
- **EUR flush preserved:** pitch 400×300 EXACT ⇒ 8/layer rotation-flush,
  100% efficiency, 5-high 1710 mm cube (unchanged, G6 figures).
- Corners rounded 15 mm; panels dished 1.5 mm; v1.0 dovetail parameters
  retained in the dataclass as lineage only.

### Mating chain

```
crate ──slide──> empty cell (row/column, any direction) ──flag down──> LOCK
  └─ stack: bottom ribs → top grooves, 2-DOF slide, drop = lock (8-high envelope)
```

## 2. AEQUBUCKET family — JB-8-32 progressive screw

```
      AEQUCAP-U (universal: one part, two duties)
   ┌───────────────────────────┐  ─┐
   │ ♀ female thread pocket    │   │  lid duty: pocket + gasket
   │ ◉ gasket seat (TPE 4×1.5) │   │  seat the bucket male ring
   │      cap body             │ 22 │
   │ ♂ male thread ring        │   │  base duty: ring screws into
   └───────────────────────────┘  ─┘  next unit's female pocket

      AEQUBUCKET-Xn
   ┌────────────┐  ─┐
   │ ♂ male ring│ OD−24   JB-8-32: pitch 8 × 4 starts = lead 32
   │   (thread) │          window χ 22 mm → draw 16 mm
   │ taper 4.2° │ body     closure 0.500 turn = 180° (half turn)
   │            │ h        2×Ø5 anti-backspin ratchet pins
   │ ◍◍◍ domes  │  ─┘      3×Ø22 domes, web 0.30 (drill sites, -D/-V)
   └────────────┘
```

### Thread-OD interface table (engine-computed equality)

| unit / cap | male ring Ø | mates female Ø | exact? |
|---|---|---|---|
| H20 ↔ U300 | 276 | 276 | ✓ |
| H10 ↔ U246 | 222 | 222 | ✓ |
| H5 ↔ U246 | 166 | 222 | ✗ stacking-lid only **[G7]** |
| H2.5 ↔ U148| 124 | 124 | ✓ (G6 correction: was misregistered to H5) |
| P1 ↔ U105  |  81 |  81 | ✓ |
| P0.5 ↔ U76 |  52 |  52 | ✓ |
| X ↔ X (same size, direct) | OD−24 | OD−24 | ✓ all six |

**Cross-size chaining:** v1.0 is same-size-major (G7). Chain length is
unlimited within one size; the family multiplies volume by vertical repetition,
not by diameter change.

### Dimension table (engine `geometry`)

| SKU | OD | h | taper | L nominal | male ring | cap |
|---|---|---|---|---|---|---|
| H20 | 300 | 353.294 | 4.2° | 20.0 | 276 | U300 |
| H10 | 246 | 260.316 | 4.2° | 10.0 | 222 | U246 |
| H5  | 190 | 226.529 | 4.2° |  5.0 | 166 | U246 [G7] |
| H2.5| 148 | 194.288 | 4.2° |  2.5 | 124 | U148 |
| P1  | 105 | 148.514 | 2.5° |  1.0 |  81 | U105 |
| P0.5|  76 | 159.583 | 2.5° |  0.5 |  52 | U76 |

*Rim heights are DERIVED (deterministic bisection, tol 1e-6 mm) from the
locked OD/taper/nominal triples — they are computed values, not specified
ones (G6).*

## 3. Nesting & stacking (engine `pallet`)

- 10 L in 20 L dead-nest depth: **204.3 mm** (12 mm wall-gap rule).
- Nested 5-stack fill: **47.9%** of upright [LITERATURE] (G4).
- EUR 1200×800 lattices: crate **8/layer rotation-flush (100%)** ×5 layers =
  1710 mm; bucket20 **8/layer** ×4 (cube-capped) = 1693 mm; bucket10 12/layer
  ×5 = 1612 mm.

## 4. Drain-site detail (-D/-V variants)

```
   base web:  3 × Ø22 dome, thinned web 0.30 mm
   punch:     AEQUTQ-PG4 gauge, Ø4 hole, F = 97 N ≤ 200 N (engine)
   -D (drain):  punch 3 sites (full drain)
   -V (vent):   punch 1 site (air bleed, hot-fill / fermenting)
```

## 5. Crate stack / block modes

```
mode A  column: 5-high on EUR (1710 mm) — corner FOS 2.69, land FOS 3.58
mode B  block:  2×2 latched (yaw-locked) — hand-portable harvest block
mode C  slide-in: guard travel ±45 mm lets a latched pair glide off a bench
```

Design envelope is checked at **8-high** (212.4 kg bottom-column load) — above
the 5-high transport duty (margin is intentional; engine `loads.stack_weight_n(8)`).
