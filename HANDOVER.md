# Handover Notes

For: the research assistant continuing this work
From: Hina Farheen (hina.farheen1234@gmail.com)
Date: 2026-08-04

## Status

The thesis is complete (`docs/Hina_Farheen_Thesis_v3.pdf`, `docs/Thesis_Defense.pptx`).
This repo contains the underlying data pipeline and analysis code so the work can
continue: further process mining, additional breakdowns, or extending the dataset.

<!-- TODO (Hina): fill this in — what specifically should the RA pick up next?
     e.g. "extend the Bayesian net to include X", "re-run on the 2023-2024 extract",
     "the surgeon-level frequency maps need X fixed" -->
**Next steps:** _add your priorities here before sharing this repo._

## What's in this repo vs. what to read first

1. **Read the thesis PDF first.** The notebooks have minimal inline documentation
   (mostly just section headers like "By Surgery Type" / "By Location") — the thesis
   write-up is the actual explanation of methodology, findings, and interpretation.
2. `notebooks/Final_Working.ipynb` is the main pipeline: cleaning →
   process discovery (pm4py heuristics miner, DFG) → surgery-duration bar charts.
3. `notebooks/beysian.ipynb` builds the Bayesian process map (`figures/process_maps/Beysian/`).
4. `figures/` holds pre-generated outputs so you can see results without re-running
   anything immediately.

## Data handling — read before touching `data/`

The dataset is **encrypted** and excluded from git in plaintext. See
[`data/README.md`](data/README.md) for the decrypt command. You'll get the passphrase
from Hina directly (Signal/WhatsApp/in person), never through this repo.

This is real patient-level perioperative data (DOB, exact timestamps, location, surgeon
IDs). Treat any decrypted copy, and any output derived from it that could re-identify
individuals, with the same care — don't upload it elsewhere, don't attach it to
issues/PRs, don't include real values in shared notebooks output cells if you re-run
and share diffs.

## Environment

See the main [`README.md`](README.md) for setup. In short: Python 3.x, packages in
`requirements.txt`, plus the Graphviz system binary for network visualizations.

## Issues fixed during handover prep (so you don't hit them fresh)

- `notebooks/Final_Working.ipynb` referenced `matplotlib.pyplot` (`plt`) and `seaborn`
  (`sns`) without importing them — this would only have worked if they were already
  defined in a live kernel session. Imports were added to the first cell.
- Both notebooks read the CSV via a bare filename (`Perioperative_Dataset_csv.csv`),
  which only works if the notebook's working directory happens to contain the file.
  Changed to `../data/Perioperative_Dataset_csv.csv`, which is correct when Jupyter is
  launched from the `notebooks/` folder (its default behavior).

## Known gaps / things worth checking

<!-- TODO (Hina): add anything you know is incomplete, fragile, or was a known
     limitation in the thesis — e.g. specific surgeon/location subsets with sparse
     data, manual steps not yet scripted, etc. -->

## Contact

hina.farheen1234@gmail.com — reach out with questions about methodology, data
provenance, or access to anything not included here.
