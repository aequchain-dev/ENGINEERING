# AEQUCRATE-400 — v1.2 BLUEPRINT (LATTICE-TRACK)

| field | value |
|---|---|
| document ID | AEQUCRATE-400-BP-120 |
| part | AEQUCRATE-400 (unibody harvest crate, Rubik-class lattice element) |
| version | **v1.2 "lattice-track"** (supersedes v1.1 hash-rail, v1.0 dovetail) |
| status | **[BLUEPRINT]** — ABSUBEST-certified (8/8 `verified`, utility 6.81), pre-prototype |
| verification | engine **26/26** · tests **21/21** · run-twice **diff = 0** — re-executed 2026-10-22 |
| truth source | `engine/geometry.py` (Crate) + `engine/loads.py` — engine supersedes all in-thought figures (G6) |
| revision lineage | `/tmp/opencode/crate_hashrail_revision.xd` (v1.1) → `/tmp/opencode/crate_latticetrack_v12.xd` (v1.2, SUPERSEDES) |
| family context | `AEQUBIN master.md` (§6.1 crate, §17 ledger G8/G9) — this file is the crate-only consolidation |
| date | 2026-10-22 |

---

## §1 IDENTITY & REVISION LINEAGE

| rev | architecture | origin | instrument evidence |
|---|---|---|---|
| v1.0 | full-perimeter **dovetail slide-latch** (tongue top-rails ×4, base grooves ×4, key-notch, ±45 mm travel) | original brief (beer-crate size, groove latch, slide) | deliberation.run elite C1 (utility 0.86, 3 laps, `structural_convergence`); ABSUBEST 8/8 `verified` 7.55 |
| v1.1 | **HASH-RAIL**: half-lap # rails on all four faces; living-hinge bridges at crossings; slider flag | user revision: Rubik-lattice, omni-hinge at crossings, empty-cell slide, optional lock, unibody | laya E222 **discarded**; deliberation.run zero-payload **discarded**; points glyph 1 lap 5.0; 6-thought lock (1 revision); ABSUBEST 8/8 `verified` 6.81 |
| v1.2 | **LATTICE-TRACK**: rails promoted to all 12 edges; detents at EVERY pitch; climb mode | user-found R-G gap: "no crate can connect to rails and slide UP + lock per position; both horizontal AND vertical" | `revise_glyph` SUPERSEDES lineage (sequential-thinking server down post-restart); engine climb check added |

## §2 REQUIREMENTS (user briefs, consolidated)

1. Rail/lip system identical on all four sides, **# shaped** (v1.1 brief)
2. **Vertical + horizontal semi-locked slide** via rail interlock
3. **Omni-directional hinge at the hash crossings**: slide off rail into full lock
4. Empty row/column cells admit a sliding crate, which then **locks**
5. Lock is **optional** (flag); rows/columns may slide freely when unlocked
6. **UNIBODY** — one-piece injection molding; no added parts, ever
7. 100% straight verticals/horizontals **optional** → resolved as 1.5 mm dish; corners **rounded 15 mm** (best-of)
8. v1.2 brief: a crate must **connect to rails and slide UP + lock at each position**; **both axes**, any stack
9. v1.2 framing (user clarification): **NO dedicated tracks** — "stacking crates should form both horizontal + vertical tracks at each column or row; crates interlockable|interconnectable". The guide paths are an **emergent property of interconnection**; an empty cell has no path.

## §3 GEOMETRY (all values engine truth, `geometry.Crate`)

| parameter | value | note |
|---|---|---|
| module L × W × H | 400 × 300 × 310 mm | pitch EXACT — EUR flush 8/layer, 100% efficiency preserved |
| wall | 3.5 mm | PP-H + UV masterbatch |
| mass | **1.70 kg** (+0.15 vs v1.0, G8) | |
| payload | 25 kg | hand carry AND stack design load (unified) |
| side-face rails | half-lap **#** — 2 vertical + 2 horizontal per face, width 8.0 mm, **proud 2.0 / recessed 2.0** | envelope = mid-plane ⇒ pitch exact |
| top / bottom | female **# grooves** depth 4.0 / male **# ribs** 4.0 × 8.0 | vertical 2-DOF slide + drop-lock |
| crossings | 4 per face (quarter points) | |
| bridge (hinge latch) | 24 × 10 mm on **0.4 mm PP living hinge**, snaps **1.2 mm detent** | latch ONLY — never carries (G8) |
| bearing pads | **40 × 40 mm** at crossings | column load path (shoulder-step transfer) |
| slider flag | 12 × 6 × 2 mm, one per face | raised = FREE-SLIDE; lowered = LOCK armed |
| v1.2 edges | **all 12 edges = full-length half-lap tracks** (4 vertical × 310; 8 horizontal full length) | engaged crates ⇒ continuous paths per column AND per row |
| v1.2 detents | **at EVERY pitch** — vertical 310, horizontal 400/300 | lock at ANY crate position |
| corners / panels | R15 rounded / 1.5 mm dish | brief options resolved |
| hand recesses | 5 (2 long ×2 + 1 short) | |
| legacy (v1.0) | dovetail params retained in dataclass for lineage only | superseded |

## §4 MECHANICS — MODES

| mode | mechanism | axis |
|---|---|---|
| SLIDE (semi-locked) | flag raised pins bridges flat; crate slides along the paths **formed by its interlocked neighbors** | in-row X/Y; in-stack 2-DOF; **climb UP/DOWN a column, ALONG a row (v1.2)** |
| LOCK (full) | flag lowered; bridge snaps into 1.2 mm detent at registered position | **every pitch position** |
| LAYER SLIDE (Rubik) | whole row or whole column slides one cell as a unit | any direction |
| SEPARATE | guided slide back along the formed path; uplift resisted by rail-root tear | tool-free |

**No-tracks rule (framing, per user):** the paths do not exist as components —
they are the **aligned rail+channel lines of engaged crates**. One part; the
lattice builds its own guides. An empty cell shows no path.

## §5 LOADS (engine, 2026-10-22 runs) [SPEC→UNVALIDATED G1]

| check | computed | limit | margin |
|---|---|---|---|
| corner transfer (8-high, loaded column 213.6 kg) | σ 3.74 MPa | 10 MPa creep | **FOS 2.67** ≥ 2.5 |
| rim land (×3 flow) | σ_eff 2.81 MPa | 10 MPa | **FOS 3.56** ≥ 3.5 |
| crossing pads, 2-pad conservative | σ 0.655 MPa | 10 MPa | **FOS 15.3** (4-pad: 30.6) |
| rail key (lattice sway) | 49 N on 2×880 mm² roots | τ 8 MPa | **FOS 287.2** |
| pair separation (root-tear governing) | 14,080 N | 800 N two-person lift | **FOS 17.6** |
| **climb hold (v1.2, loaded 262 N on 528 mm²)** | σ 0.496 MPa | 10 MPa | **FOS 20.2** |
| hinge latch | web 0.4 / detent 1.2 | latch-only by construction | G8 |

## §6 VERIFICATION STATE

- Engine verify **26/26 PASS** (7 crate checks: corner, land, pitch-preserved,
  pads, key, separation, hinge-latch-only, climb, every-pitch detents)
- Tests **21/21 PASS** (mutation-sensitive; run-twice-diff-zero included)
- ABSUBEST v1.1 certificate: 8/8 stages `verified`, utility 6.81,
  `gap_detected: true` — honestly recorded
- Glyph lineage: v1.1 → v1.2 via SUPERSEDES edge (no silent revision)

## §7 MANUFACTURE (summary; SOPs in `AEQUBIN_MFG.md`)

- **M1 mold, 450 t press, single-gang — still ONE part (13 SKUs/12 molds unchanged)**
- Side-action cores: half-lap channels + female groove undercuts
- Living-hinge bridges molded in-flow (gate keeps melt front through hinge zone <1 s)
- Repair: PP hot-air weld; hinge re-weld at 0.4 mm gauge, 20-cycle flex test

## §8 RESIDUAL GAPS (crate-specific)

| ID | gap | class |
|---|---|---|
| G8 | living-hinge fatigue [LITERATURE] until **T8** (10k slide/lock cycles); pads carry, hinges latch | [SPEC→UNVALIDATED until T8] |
| G9 | climb **dynamic snatch loads** until **T9** (loaded climb, 100 snatch stops); static FOS 20.2 engine-computed (in-thought 16.1 superseded per G6) | [SPEC→UNVALIDATED until T9] |

## §9 DISCLOSURE

Executed 2026-10-22: full suite (21/21), double-run diff-zero, verify 26/26.
Instrument chain v1.1/v1.2: laya E222 discarded (defect); deliberation.run
degenerate payload discarded ×2; answers carried by vexl-points-reasoning
(1 lap, 5.0; revise_glyph SUPERSEDES for v1.2) + sequential-thinking (6
thoughts, 1 explicit revision; server unavailable post-restart for the v1.2
loop — revise_glyph substituted). Engine supersedes all in-thought figures.
No prototype, no FEA, no hinge-fatigue data yet — this is a [BLUEPRINT].

*AEQUCRATE-400-BP-120 — part of the AEQUBIN v1.0 engineering folder.*
