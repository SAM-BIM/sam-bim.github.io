# Evidence assets manifest

This directory holds the curated evidence captures referenced by the SAM
website. Every image here is a real screenshot of SAM software. Nothing is
mocked up, AI-generated or edited beyond cropping.

## Drop-in procedure (remaining IDs)

1. Save the capture with the exact filename below.
2. In `index.html`, find the matching `EVIDENCE SLOT` / `VIDEO SLOT` /
   `ARCHITECTURE SLOT` comment and insert a `<figure class="shot">` following
   the E01–E04 figures (image `width`/`height` attributes set to the file's
   pixel size, meaningful `alt`, caption with the ID).
3. Record the capture provenance below and set its status to `CAPTURED`.

## Manifest

Status vocabulary: `CAPTURED` — the real screenshot/diagram is committed in
this directory and wired into the page; `PENDING` — the slot is marked in
`index.html` and the capture is outstanding (not rendered on the page).

| ID | Filename | Website location | Caption (as published) | Priority | Status |
|---|---|---|---|---|---|
| E01 | `E01_SAM_PartF_Design_Airflow_Overlay.png` | Hero; social preview image | Part F airflow requirements and engineering design values reviewed directly on the SAM analytical model. (Legend: F = Part F requirement, D = design airflow.) | Primary | CAPTURED |
| E01 (detail) | `E01_SAM_PartF_Design_Airflow_Overlay_Detail.png` | Workflow step 01 | Bedroom supply: Part F requires 63 l/s; the design holds 143 l/s. Two quantities on one plan. | Primary | CAPTURED |
| E02 | `E02_SAM_PartO_Review_Iteration_Authority.png` | Workflow step 02 | The regulatory requirement, engineering design and selected equipment capacity remain separate decisions. | Primary | CAPTURED |
| E03 | `E03_SAM_PartO_Prepare_Run_Status.png` | Workflow step 03 | SAM materialises the engineering design into a deterministic simulation scenario and records the run state. | Primary | CAPTURED |
| E04 | `E04_SAM_PartO_TM59_Result.png` | Workflow step 04 | Example TM59 assessment showing the recorded room-level outcome; SAM reports the result rather than forcing a pass. | Primary | CAPTURED |
| E05 | `E05_SAM_PartO_Iteration2B_Optimisation.png` | Engineering depth — HVAC & ventilation | Iteration 2B capacity-ceiling optimisation | Secondary | PENDING |
| E06 | `E06_SAM_Analytical_Model_Context.png` | Reserved (SAM README screenshot strip) | Analytical model in context | Primary | PENDING |
| E07 | `E07_SAM_AHU_Mollier.png` | Engineering depth — Psychrometrics | Air-handling processes on the Mollier chart | Secondary | PENDING |
| E08 | `E08_SAM_Release_Validation_H1_H12.png` | Engineering depth — Engineering validation | H1–H12 release acceptance evidence | Secondary | PENDING |
| E09 | `E09_SAM_Revit_Integration.png` | Engineering depth — BIM/BEM interoperability | Revit integration | Secondary | PENDING |
| V1 | (video, ~3 min) | Workflow section (VIDEO SLOT comment) | Flagship end-to-end workflow demonstration | Planned | PENDING |
| D1 | (diagram) | Platform section (ARCHITECTURE SLOT comment) — replaces the CSS stack | SAM platform architecture diagram | Planned | PENDING |

## Provenance of E01–E04 (captured 2026-09-16)

All four were captured in one continuous session on 2026-09-16, from the real
`SAM Analytical.exe` desktop app driven through its own UI (the same UI
Automation route as the SAM#111 Part O acceptance harness). Nothing was
simulated, typed into a result or edited outside the application.

| Item | Value |
|---|---|
| Build | Release, `/t:Rebuild`, 0 errors, 2026-09-16 22:41, from `sow/2026-Q3` tips: SAM `e2c0e2c0`, SAM_Systems `05ca0c18`, SAM_Tas `c267f52f`, SAM_UI `9f515c4c` |
| Simulation engine | EDSL Tas 9.5.7 (licensed), full year, days 1–365 |
| Model | Three-dwelling residential model (Flat 1 / 2 / 3 + corridor, 8 assessed rooms): a fresh copy of the model used for the SAM#111 real-project acceptance (source SHA-256 `a7e09a25…`). Model name `000000_SAM_AnalyticalModel-It1a-futureZ1`; no client, address or project identifiers. |
| Weather | The model's own CIBSE DSY 2050s design weather (`Z1_DSY1_2050s_HIGH90`) |
| Route | Simulate → Part O Prepare & Run → Iteration 2 (automatic catalogue selection) → Tas → TM59 → Optimise (Iteration 2B, 5 l/s step, limit 10) |
| Outcome | TM59 **FAIL** after Iteration 2 (6 of 8 rooms) and after the last valid 2B round, run 10 (6 of 8 rooms). Room figures reproduce the SAM#111 acceptance record exactly. |

| File | Pixels | Screen | What it shows |
|---|---|---|---|
| E01 | 1604 × 568 | Main window, plan view `Level 0`, *Part F Airflow* overlay (annotation scale 1:150) + *Ventilation Design* overlay, after 2B | Flat 1 and Flat 2: F tags = Approved Document F requirement, D tags = design airflow held by the model (e.g. bedroom supply F 63 / D 143 l/s). Transfer tags carry SAM's own "?" status (no modelled transfer opening identified). |
| E01 detail | 1095 × 532 | Same view, zoomed on Flat 2 | Bedroom, kitchen and ensuite tags at legible size |
| E02 | 1116 × 368 | *Part O — Iteration 2B — TM59 optimisation* window, grids scrolled to run 10 | Design airflow history (design before / requested / achieved / Part F required / TM59) and serving-unit history (duty 143/143 vs max 150/150, headroom 7/7, product kept) |
| E03 | 1345 × 904 | Main window plan + *Part O — Prepare & Run* hub, Iteration 2 selected, after the run | Scenario, automatic catalogue selection, Max as capability ceiling, configuration status and Simulation / Results READY |
| E04 | 1345 × 730 | Main window plan + *Part O — Overheating (TM59)* window for run 10, report scrolled to the verdict | TM59 occupied-space assessment FAIL and the per-room mechanical-ventilation table |

Preparation: crop only, from window captures (`PrintWindow`) or a 1920 × 1080
screen frame with no scaling, annotation or retouching. Crops remove the
Windows title bar and taskbar, and in E04 the window's summary line, which
held a local output path. E03 and E04 are single real screen states (a dialog
over the main window), not composites. The Review-iteration notes panel and
the 2B notes panel, which list local paths, are outside the crops.
Source frames were 1920 × 1080 at 100 % Windows scaling, so the E01–E04
widths are native pixels and have not been upscaled.

## Rules

- Captures are real screenshots of capability merged on the `sow/2026-Q3`
  release line, taken from a Release build of that line.
- Allowed preparation: crop, scale, and captions/annotation *outside* the
  software image. A composite of two legitimate views must be labelled as one.
- Part O Iterations 1a / 1b / 2 / 2B (frozen 2026-09-08) may be shown as
  validated capability. Do not show an Iteration 2 acoustic-restriction, bypass
  or boost result: those behaviours are not implemented.
- Part O Iteration 3 may appear only as **in progress**, and only as what is
  evidenced: the frozen, licensed-accepted foundation route (explicit MVHR
  systems in Tas Systems, Reference A vs Candidate B) or the selected-product
  cooling mode. Never present Iteration 3 as complete (tracker
  [SAM#111](https://github.com/SAM-BIM/SAM/issues/111) is open), never show
  manufacturer heat-recovery or fan behaviour (evidence-blocked, fails closed),
  and never caption a failing TM59 run as a pass.
- No client or project-identifying data, personal or employer file paths,
  usernames, taskbars or other desktop chrome in frame.
- PNG source captures; keep them legible at ~1100 px rendered width.
- Do not commit dummy or AI-generated imagery.
