# AEQUBIN v1.0 — MANUFACTURING (SOPs & tooling)

| field | value |
|---|---|
| document ID | AEQUBIN-MFG-100 |
| status | **[SOP]** procedures (equipment/process classes [SPEC]) |
| tooling basis | 12 injection part-types (engine-derived census, G6) |

## 1. Tooling map

| mold station | parts | press class | notes |
|---|---|---|---|
| M1 crate | AEQUCRATE-400 (v1.1 hash-rail) | 450 t | single-gang; **side-action cores** for half-lap channels + female groove undercuts; **living-hinge bridges (0.4 mm web) molded in-flow** (gate layout keeps melt front through hinge zone <1 s); bearing pads + slider-flag undercuts via lifters; UV MB |
| M2–M7 buckets | H20/H10/H5/H2.5/P1/P0.5 | 250–350 t | family tooling: shared base-dome insert set; per-size cavity |
| M8–M12 caps | U300/U246/U148/U105/U76 | 150–250 t | **2-station 2K**: PP-H body + TPE-70A second-shot ring |
| — | AEQUTQ-PG4 | — | machined (tool steel) + PP-H handle, not molded |

Regional-shop constraint (EFE social pillar): largest press is the 450 t crate
tool; all other parts run on 150–350 t. No auxiliaries beyond 2K rotary or
two-cylinder injection units.

## 2. SOP-2K: universal cap overmold

1. **Shot 1 (PP-H):** mold cap body; gate at rim (off gasket face); hold 60–80%
   of nominal cycle; demold *into* second station via rotary/transfer plate.
2. **Shot 2 (TPE-70A):** inject 4.0 × 1.5 mm ring into the gasket groove;
   substrate ≥120 °C at shot time for bond (SEBS-class adhesion, no primer).
3. **Accept:** pull-peel adhesion > cohesive tear of the TPE (shop tensile
   coupon per lot); compression set coupon 8% @72 h/23 °C per material cert.
4. **No loose-part gasket is permitted anywhere in the family** (design rule;
   removes the classic lost/sealed-wrong failure mode).

## 3. SOP-PUNCH: engineered drain sites (-D/-V)

1. Bucket base carries 3 × Ø22 domes with 0.30 mm thinned web (mold-formed;
   no post-mold drilling of virgin wall — that is the whole point).
2. Fit the **AEQUTQ-PG4** gauge over the dome; punch through with hand press
   or mallet blow. Computed punch force **97 N ≤ 200 N hand limit** (engine).
3. **-D (drain):** punch all 3 sites. **-V (vent):** punch 1 site (air bleed
   for hot-fill/closure). Leave webs intact on sealed-duty units.
4. Deburr by gauge chamfer; visual: web remnant ring ≤0.5 mm.

## 4. SOP-WELD: repair (regional skill, EFE social pillar)

1. **Crate rail/land crack:** PP hot-air weld with PP-H rod (same PCR-30
   family); V-grind 2 mm, weld, re-profile against the rail gauge; post-weld
   rail root section ≥ 90% of nominal (root 880 mm² conservative per engaged
   rail; uplift governing mode 14,080 N / FOS 17.6, engine). **Living-hinge
   bridges are weld-repairable**: weld the web back at 0.4 mm gauge (hinge
   template), flex-test 20 cycles before release.
2. **Bucket ring damage:** if male ring thread is stripped, weld-fill and
   re-chase with the JB-8-32 chase gauge; if beyond repair, the **base-cap
   duty of the matching AEQUCAP-U restores the joint** (cap male ring is the
   same thread standard) — this is the field-repair path of the universal cap.
3. **Gasket renewal:** weld a fresh TPE bead into the cap groove, re-chamfer;
   compression 25% verified by feeler (0.9–1.1 mm seated gap).

## 5. Process notes

- **Regrind loop:** runners + defected parts reground to ≤25% blend into the
  *same part-type* stream (mono-material rule keeps this legal and infinite).
- **Crate stacking orientation:** parts ship nested 8/layer rotation-flush;
  no in-mold labeling needed (key-notch marks orientation).
- **Tolerances [SPEC]:** linear ±0.35% (≤±1.05 mm at 300 mm); thread pitch ±0.5%
  with lead-32 4-start form gauges; dome web 0.30 +0.05/−0.05 mm.
- **Volume acceptance:** fill-to-rim nominal ±18% (verify check) — at ±1.05 mm
  rim tolerance the computed volume excursion is ≈±0.9% [SPEC], well inside.

## 6. Mold qualification gate

Before PPAP-style release: (a) run-twice geometric sampling — 2 shots ×2 cavities
×3 dimensions measured, diff ≤ tolerance; (b) cap 2K pull-peel; (c) punch force
≤200 N measured on 10 domes; (d) half-turn closure on gauge rings (no more than
0.55 turn to seat, no less than 0.45). These mirror the engine's invariants
(TEST.md matrix) — the plant executes the same numbers the engine computes.
