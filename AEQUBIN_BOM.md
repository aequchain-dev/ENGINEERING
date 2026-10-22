# AEQUBIN v1.0 — BILL OF MATERIALS

| field | value |
|---|---|
| document ID | AEQUBIN-BOM-100 |
| status | **[SPEC]** — numbers engine-generated |
| machine source | `registry/parts.json` (minted by `python -m engine.cli registry --dump`) |
| census | **13 SKUs · 12 injection part-type molds** (engine-derived, G6) |

All masses/materials from `engine/materials.py` (PP-H 905 kg/m³; TPE-70A 4%
mass share). Quantities are per named assembly, not per pallet.

## 1. Assembly: AEQUCRATE-400 harvest crate

| item | part | material | qty | notes |
|---|---|---|---|---|
| 1 | AEQUCRATE-400 body (single-gang molded, **v1.1 hash-rail unibody**) | PP-H + UV MB | 1 | 400×300×310, wall 3.5, **1.70 kg** (+0.15 G8), 5 hand recesses |
| — | half-lap # rails + ♀ grooves / ♂ ribs + living-hinge bridges + pads + flags | integral PP-H | — | not separate parts (molded-in, unibody) |
| — | corner blocks 40 mm + R15 corners + 1.5 mm panel dish | integral PP-H | — | rounded/best-of per G8 |

*No fasteners, no seals, no sub-assemblies. Tool-free by design.*

## 2. Assembly: AEQUBUCKET-Xn (per size)

| item | part | material | qty | notes |
|---|---|---|---|---|
| 1 | bucket body | PP-H | 1 | see table below |
| 2 | AEQUCAP-U… universal cap | PP-H + TPE-70A (2K) | 0–2 | 0 = direct bucket↔bucket; 1 = lid; 2 = lid+base adapter |
| 3 | (opt) drain sites | punched PP web | 3× Ø4 | **-D/-V** variants only; punched with AEQUTQ-PG4 |

### 2.1 Bucket bodies (engine geometry)

| SKU | OD mm | h mm | taper | nominal L | male ring Ø | wall class |
|---|---|---|---|---|---|---|
| AEQUBUCKET-H20 | 300 | 353.294 | 4.2° | 20.0 | 276 | 3.0 (class, [SPEC]) |
| AEQUBUCKET-H10 | 246 | 260.316 | 4.2° | 10.0 | 222 | 3.0 |
| AEQUBUCKET-H5  | 190 | 226.529 | 4.2° |  5.0 | 166 | 3.0 |
| AEQUBUCKET-H2.5| 148 | 194.288 | 4.2° |  2.5 | 124 | 2.5 |
| AEQUBUCKET-P1  | 105 | 148.514 | 2.5° |  1.0 |  81 | 2.0 |
| AEQUBUCKET-P0.5|  76 | 159.583 | 2.5° |  0.5 |  52 | 2.0 |

Body wall classes are [SPEC] starting values, tuned per size at mold
qualification; the governing structural checks (thread FOS 49.1, punch 97 N)
hold at these values (engine).

### 2.2 Universal caps (one part = lid or base)

| SKU | Ø mm | male ring OD | female pocket OD | gasket section | duty |
|---|---|---|---|---|---|
| AEQUCAP-U300 | 300 | 276 | 276 | 4.0 × 1.5 TPE-70A | H20 lid/base |
| AEQUCAP-U246 | 246 | 222 | 222 | 4.0 × 1.5 | H10 lid/base; **H5 stacking-lid only [G7]** |
| AEQUCAP-U148 | 148 | 124 | 124 | 4.0 × 1.5 | H2.5 lid/base |
| AEQUCAP-U105 | 105 |  81 |  81 | 4.0 × 1.5 | P1 lid/base |
| AEQUCAP-U76  |  76 |  52 |  52 | 4.0 × 1.5 | P0.5 lid/base |

Gasket: 2K overmold-bonded, 25% compression — **no separate part, no assembly
step, no lost-part failure mode.**

## 3. Tooling & accessories

| SKU | kind | material | purpose |
|---|---|---|---|
| AEQUTQ-PG4 | tool (machined) | tool steel + PP-H handle | Ø4 dome punch gauge for -D/-V drain/vent variants (punch force 97 N ≤ 200 N hand) |

## 4. Materials summary (engine `materials_summary`)

| stream | composition | recycle |
|---|---|---|
| bodies | PP-H (food-grade, MFI 10–12, PCR ≥30%, UV MB on crate) | code 5, infinite mechanical |
| seal | TPE-70A SEBS-class, food-contact | code 5, same stream (4% mass) |
| gauge | tool steel + PP-H handle | metal stream + code 5 |

**Mono-stream rule:** PP-H 96% + TPE 4% share PP recycle class — whole family
(except the machined gauge) is one recycle stream.

## 5. Procurement bands [SPEC]

Unit-cost targets are declared as a **band** in the OPTIBEST economic
certification: regional-shop injection at 250–450 t presses, PCR-30 feed,
12 part-types amortized over 4 mold-families of core inserts (see
`AEQUBIN_MFG.md` §tooling). Costs are [SPEC] targets pending quotes — no
fabricated euro values are stated in this BOM (honesty rule: no numbers
without a source).
