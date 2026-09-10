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
3. Update the `Present` column below and the site README if the set changes.

## Manifest

| ID | Filename | Website location | Caption (intended) | Status | Present |
|---|---|---|---|---|---|
| E01 | `E01_SAM_PartF_Design_Airflow_Overlay.png` | Hero + Workflow step 01 | Part F design airflow overlay on the analytical model | Required — primary | No |
| E02 | `E02_SAM_PartO_Review_Iteration_Authority.png` | Workflow step 02 | Part O iteration review showing decision authority | Required — primary | No |
| E03 | `E03_SAM_PartO_Prepare_Run_Status.png` | Workflow step 03 | Part O prepare/run status | Required — primary | No |
| E04 | `E04_SAM_PartO_TM59_Result.png` | Workflow step 04 | TM59 assessment result | Required — primary | No |
| E05 | `E05_SAM_PartO_Iteration2B_Optimisation.png` | Engineering depth — HVAC & ventilation systems | Iteration 2B capacity-ceiling optimisation | Required | No |
| E06 | `E06_SAM_Analytical_Model_Context.png` | Reserved (contact section / SAM README screenshot strip) | Analytical model in context | Required — primary | No |
| E07 | `E07_SAM_AHU_Mollier.png` | Engineering depth — Psychrometrics | Air-handling processes on the Mollier chart | Required | No |
| E08 | `E08_SAM_Release_Validation_H1_H12.png` | Engineering depth — Engineering-software validation | H1–H12 release acceptance evidence | Required | No |
| E09 | `E09_SAM_Revit_Integration.png` | Engineering depth — BIM/BEM interoperability | Revit integration | Required | No |
| V1 | (video, ~3 min) | Workflow section footer (VIDEO SLOT comment) | Flagship end-to-end workflow demonstration | Planned | No |
| D1 | (diagram) | Platform section (ARCHITECTURE SLOT comment) — replaces the text stack | SAM platform architecture diagram | Planned | No |

## Rules

- Captures are real screenshots of the shipped `sow/2026-Q3` capability only.
  Nothing from the unfinished Part O Iteration 3 route.
- PNG for screenshots; keep them legible at ~1120 px content width.
- Do not commit dummy or AI-generated imagery.
