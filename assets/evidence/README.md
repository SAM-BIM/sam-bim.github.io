# Evidence assets manifest

This directory holds the curated evidence captures referenced by the SAM
website. **No binary placeholders are committed.** Each asset below has a
styled placeholder slot in `index.html` (marked `data-evidence="E.."`) that
renders cleanly until the real file is dropped in here.

## Drop-in procedure

1. Save the capture with the exact filename below.
2. In `index.html`, find the matching `data-evidence` slot (or the
   `EVIDENCE SLOT` / `VIDEO SLOT` / `ARCHITECTURE SLOT` comment) and replace
   the placeholder `<div class="evidence-slot">…</div>` with a `<figure>`,
   following the commented example in the hero (E01).
3. Update the `Status` column below to `CAPTURED` and the site README if the set changes.

## Manifest

Status vocabulary: `CAPTURED` — the real screenshot/diagram is committed in
this directory and wired into the page; `PENDING` — the placeholder slot is
live and the capture is outstanding.

| ID | Filename | Website location | Caption (intended) | Priority | Status |
|---|---|---|---|---|---|
| E01 | `E01_SAM_PartF_Design_Airflow_Overlay.png` | Hero + Workflow step 01 | Part F design airflow overlay on the analytical model | Primary | PENDING |
| E02 | `E02_SAM_PartO_Review_Iteration_Authority.png` | Workflow step 02 | Part O iteration review showing decision authority | Primary | PENDING |
| E03 | `E03_SAM_PartO_Prepare_Run_Status.png` | Workflow step 03 | Part O prepare/run status | Primary | PENDING |
| E04 | `E04_SAM_PartO_TM59_Result.png` | Workflow step 04 | TM59 assessment result | Primary | PENDING |
| E05 | `E05_SAM_PartO_Iteration2B_Optimisation.png` | Engineering depth — HVAC & ventilation systems | Iteration 2B capacity-ceiling optimisation | Secondary | PENDING |
| E06 | `E06_SAM_Analytical_Model_Context.png` | Reserved (contact section / SAM README screenshot strip) | Analytical model in context | Primary | PENDING |
| E07 | `E07_SAM_AHU_Mollier.png` | Engineering depth — Psychrometrics | Air-handling processes on the Mollier chart | Secondary | PENDING |
| E08 | `E08_SAM_Release_Validation_H1_H12.png` | Engineering depth — Engineering-software validation | H1–H12 release acceptance evidence | Secondary | PENDING |
| E09 | `E09_SAM_Revit_Integration.png` | Engineering depth — BIM/BEM interoperability | Revit integration | Secondary | PENDING |
| V1 | (video, ~3 min) | Workflow section footer (VIDEO SLOT comment) | Flagship end-to-end workflow demonstration | Planned | PENDING |
| D1 | (diagram) | Platform section (ARCHITECTURE SLOT comment) — replaces the text stack | SAM platform architecture diagram | Planned | PENDING |

Status last checked 2026-09-16: no approved capture exists for any ID. Working
screenshots found on the development machines were not used — they are not
approved captures, and some show local paths, desktop chrome or project data.

## Rules

- Captures are real screenshots of capability merged on the `sow/2026-Q3`
  release line, taken from a Release build of that line.
- Part O Iterations 1a / 1b / 2 / 2B (frozen 2026-09-08) may be shown as
  validated capability. Do not show an Iteration 2 acoustic-restriction, bypass
  or boost result: those behaviours are not implemented.
- Part O Iteration 3 may appear only as **in progress**, and only as what is
  evidenced: the frozen, licensed-accepted foundation route (explicit MVHR
  systems in Tas Systems, Reference A vs Candidate B) or the selected-product
  cooling mode. Never present Iteration 3 as complete (tracker
  [SAM#111](https://github.com/SAM-BIM/SAM/issues/111) is open), never show
  manufacturer heat-recovery or fan behaviour (evidence-blocked, fails closed),
  and never caption the recorded real-project run as a pass (no stage passes
  TM59 on it).
- No client or project-identifying data, personal or employer file paths,
  usernames, taskbars or other desktop chrome in frame.
- PNG for screenshots; keep them legible at ~1120 px content width.
- Do not commit dummy or AI-generated imagery.
