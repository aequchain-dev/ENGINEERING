# AEQUBIN v1.0 — engineering folder

Modular harvest/household container family: **AEQUCRATE-400** (v1.1
**hash-rail Rubik-lattice** crate — half-lap # rails on all four sides, slide
into any empty row/column cell, living-hinge snap-lock, optional lock mode)
+ **AEQUBUCKET** 0.5–20 L (screw-together buckets on the JB-8-32 half-turn
joint) + universal **AEQUCAP-U** lids/bases.

**Status: [BLUEPRINT]** — OPTIBEST/ABSUBEST certified (v1.1 revision 8/8
`verified`, utility 6.81); verify **26/26 PASS**, tests **21/21**, run-twice
**diff 0**. No prototype yet (residual gaps G1–G9, see `AEQUBIN master.md` §17).

## Layout

```
AEQUBIN/
├── AEQUBIN master.md      ODF v1.0 §1–17, decision record, gap ledger, OPTIBEST declaration
├── AEQUBIN_BOM.md         13 SKUs, 12 injection part-types, mono-stream materials
├── AEQUBIN_SCHEMATIC.md   dimension + interface chain (all engine-computed)
├── AEQUBIN_MFG.md         tooling map, 2K/punch/weld SOPs, tolerances
├── AEQUBIN_TEST.md        21-check matrix, type-test plan, mutation rule
├── engine/                deterministic Python engine (single source of truth)
│   ├── geometry.py        locked dims + DERIVED rim heights (bisection solver)
│   ├── loads.py           FOS/thread/torque/punch analytic checks
│   ├── pallet.py          EUR lattice, nesting, cube conformance
│   ├── registry.py        SKU census → registry/parts.json (data plane)
│   ├── materials.py       PP-H / TPE-70A spec data, tier ladder
│   ├── units.py           SI integrity
│   ├── verify.py          21 invariants + residual gap ledger G1–G7 + EFE pillars
│   └── cli.py             `all|geometry|loads|pallet|verify|registry [--dump]`
├── tests/test_engine.py   16 mutation-sensitive tests + run-twice-diff-zero
└── registry/parts.json    machine-readable catalog (PROGRAMMABLE data plane)
```

## Quickstart

```bash
cd engineering/AEQUBIN
python -m unittest discover -s tests -t .     # 16/16 PASS (mutation-sensitive)
python -m engine.cli all                      # full JSON: geometry+loads+pallet+verify
python -m engine.cli all > /tmp/a && python -m engine.cli all > /tmp/b && diff /tmp/a /tmp/b   # = 0
python -m engine.cli verify                   # 21/21 + gap ledger G1–G7
python -m engine.cli registry --dump          # mint registry/parts.json
```

## Headline numbers (engine-computed 2026-10-21)

- Crate 400×300×310, wall 3.5, payload 25 kg, mass 1.70 kg; **v1.1 hash-rail
  lattice**: half-lap # rails (proud 2/recess 2 → pitch exact, EUR flush 8/layer
  survives), vertical 2-DOF slide + drop-lock, living-hinge bridges at 4
  crossings/face (0.4 web / 1.2 detent), slider flag = optional free-slide;
  bearing pads 40×40 carry the column (FOS 15.3/30.6) — hinges latch, never
  carry; separation FOS 17.6; corner FOS 2.67, land FOS 3.56.
- **v1.2 lattice-track**: all 12 edges are full-length half-lap **tracks** —
  a crate can **hook onto a column ladder and CLIMB up/down, or climb along a
  row**, locking at **EVERY crate position** (per-pitch detents); static hold
  FOS 20.2 loaded; snatch loads → type test T9 (G9).
- JB-8-32 joint: pitch 8 × 4 starts (lead 32), **half-turn closure (180°)**,
  22 mm free-spin window, 16 mm draw; thread capacity 49.4 kN (FOS 49.1);
  hand torque 10.8/13.1 N·m ≤ 14; **loaded-column open is SOP-prohibited**.
- Buckets: Ø300/246/190/148/105/76, taper 4.2° (H-class) / 2.5° (P-class),
  rim heights derived to exact nominal volume; drain domes 3×Ø22 web 0.30,
  punch 97 N with the PG4 gauge.
- Logistics: crate **8/layer rotation-flush (100% efficiency)** ×5 = 1710 mm;
  bucket20 8/layer ×4 = 1693 mm; bucket10 12/layer ×5 = 1612 mm (all ≤1800).
- Sustainability: PP-H + TPE-70A mono-stream (class 5), PCR ≥30%, zero
  operational energy, EFE 7-pillar green.

## Honesty notes

- Every number in the docs is copied from executed engine output, not from
  memory. Revisions vs the first deliberation-phase figures are **disclosed**
  in the ledger (G6: pallet figures, SKU census; G7: H5 cap duty + U148
  correction).
- Decision chain: laya forward-pass **discarded** (malformed rubric,
  low confidence) → deliberation.run (elite C1, utility 0.86, 3 laps,
  structural_convergence) → points-reasoning glyph → 16-thought sequential
  lock → ABSUBEST 8/8 verified (gap flagged) → **engine supersedes all
  in-thought arithmetic**.
