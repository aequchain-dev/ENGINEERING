# AEQUBIN v1.0 — TEST (acceptance, type tests, gates)

| field | value |
|---|---|
| document ID | AEQUBIN-TEST-100 |
| status | **[SOP]** test plan + executed engine/CI results |
| executed this session | 2026-10-21, all commands exit 0 |

## 1. Executed engine gates (this session — honesty invariant #1)

| gate | command | result |
|---|---|---|
| unit suite (mutation-sensitive) | `python -m unittest discover -s tests -t .` | **21/21 PASS** |
| replicable double-run | `python -m engine.cli all` ×2, `diff` | **byte-identical (diff = 0)** |
| invariant check battery | `python -m engine.cli verify` | **26/26 PASS** |
| registry mint | `python -m engine.cli registry --dump` | parts.json written, 13 SKUs / 12 molds (v1.1 crate stays unibody) |

## 2. Invariant matrix (the 26 verify checks — all PASS)

| # | check | threshold | computed |
|---|---|---|---|
| 1 | crate.stack.corner_FOS | ≥2.5 | **2.67** (σ 3.74 vs allow 10 MPa, mass 1.70 kg) |
| 2 | crate.stack.landFlow3_FOS | ≥3.5 | **3.56** (σ_eff 2.81 MPa, ×3 flow) |
| 3 | crate.hashrail.pitch_preserved [G8] | pitch == 400×300 | exact (proud 2 == recess 2) |
| 4 | crate.hashrail.crossing_pad_FOS [G8] | ≥10 (2-pad) | **15.3** / 4-pad **30.6** |
| 5 | crate.hashrail.rail_key_FOS | ≥2.5 | **287.2** (sway 49 N on 2×880 mm² roots) |
| 6 | crate.hashrail.separation_FOS | ≥10 | **17.6** (14,080 N root-tear) |
| 7 | crate.hashrail.hinge_latch_only [G8] | web 0.4 / detent 1.2 | 0.4 / 1.2 |
| 8 | crate.latticetrack.climb_FOS [G9] | ≥10 | **20.2** (262 N on 528 mm², loaded) |
| 9 | crate.latticetrack.detents_every_pitch [G9] | 12 tracks, every pitch | 12 / pitch 310 & 400/300 |
| 10 | screw.thread.FOS | ≥40 | **49.1** (49.4 kN vs 1005 N column) |
| 11 | screw.torque | ≤14 N·m | close **10.8**, open **13.1** |
| 12 | drain.punch | ≤200 N | **97 N** (Ø4, web 0.30) |
| 13–18 | bucket.volume ×6 | ±18% of nominal | **exact nominal** (derived heights) |
| 19 | bucket.nest[10L-in-20L] | >100 mm | **204.3 mm** |
| 20 | pallet.crate.per_layer [G6] | ==8 flush | 8, layer efficiency **100%** |
| 21 | pallet.crate.cube | ≤1800 mm | 1710 |
| 22 | pallet.bucket20.per_layer [G6] | ==8 | 8 (4 layers cube-capped) |
| 23 | pallet.bucket20.cube | ≤1800 mm | 1693 |
| 24 | screw.closure.is_half_turn | 0.5 turn | 0.500 |
| 25 | caps.exact_coverage_5_of_6 [H5=G7] | 5 exact + 1 disclosed | exact: H20/H10/H2.5/P1/P0.5; H5 stacking-only |
| 26 | sku.property.mono_stream | one recycle class | PP-H 96% + TPE 4%, class 5 |

## 3. Type-test plan (physical, closes G1/G2) [UNVALIDATED until run]

| test | method anchor | acceptance | closes |
|---|---|---|---|
| T1 corner static creep | 8-high column, 25 kg/crate, 1000 h @23 °C | σ ≤3.72 MPa measured, no >2 mm corner set | G1 |
| T2 dovetail separation | servo pull, 5× latched pairs | F_sep ≥8800 N, no rail root crack | G1 |
| T3 thread column | 5 filled H20 (≈1005 N) across one joint, 24 h | no ring slip, half-turn still seats | G1 |
| T4 torque gauge R&D | instrumented lid torque wrench, dry/wet, 20 samples | 10.8/13.1 N·m envelope, loaded-open shear demo (destructive) | G2 |
| T5 punch ergonomics | 10 domes ×5 operators | ≤200 N, 100% web open | — |
| T6 stack/drop logistics | EUR column 5-high, 5 drops 500 mm | functional latch after drop | G1 |
| T7 gasket seal | 20 L water inverted, 24 h | no gravity leak at 25% compression | G1 |
| T8 hinge cycle [G8] | 10k slide/lock cycles, 4 bridges, 23 °C + −20 °C | no web crack; detent force within ±20%; flag still pins | G8 |
| T9 climb snatch [G9] | loaded climb (26.7 kg) 2-track ladder, 100 snatch stops at random pitches | no pocket/root crack; detent still seats; FOS_climb ≥ 10 retained | G9 |

## 4. Mutation rule (test-the-tests)

The suite is **required** to go red on degraded design parameters. Demonstrated
invariants: wall 3.5→3.0 mm forces corner FOS below 2.5; any taper/OD/volume
edit forces the derived-height solver to re-converge and the ±2% volume test
fails if the lock triple is violated; pallet lattice changes break the ==8
flush assertions; registry edits break the census equality. A green suite that
stays green under deliberate breakage is a failure (MCSA phase-14 rule) —
the suite's red-path is the deliverable, not an afterthought.

## 5. EFE 7-pillar audit (engine-quoted)

material ✓ · energy ✓ (zero operational) · waste ✓ (mono-stream reground) ·
water ✓ (85 °C hot-wash) · social ✓ (250–450 t regional press, weldable) ·
economic ✓ (13 SKUs/12 molds) · temporal ✓ (20+ y crate / 15+ y bucket,
tier-agnostic geometry).

## 6. Residual gaps under test (mirrors engine ledger)

G1 prototype/FEA · G2 torque analog · G3 laya evidence discarded (process
defect, closed) · G4 nesting [LITERATURE] · G5 T2/T3 materials
[ASPIRATIONAL] · G6 disclosed engine-revision record · G7 H5 cap/cross-size
chaining [SPEC→UNVALIDATED]. Full text: `python -m engine.cli verify`.
