# Handover Notes

For: the research assistant continuing this work

From: Hina Farheen

Date: 2026-08-04

## Status

The thesis is complete (`docs/Hina_Farheen_Thesis_v3.pdf`, `docs/Thesis_Defense.pptx`).
This repo contains the underlying data pipeline and analysis code so the work can

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
[`data/README.md`](data/README.md) for the decrypt command. Reach out to me for the passphrase directly.

This is real patient-level perioperative data (DOB, exact timestamps, location, surgeon
IDs). Treat any decrypted copy, and any output derived from it that could re-identify
individuals, with the same care — don't upload it elsewhere, don't attach it to
issues/PRs, don't include real values in shared notebooks output cells if you re-run
and share diffs.

## Environment

See the main [`README.md`](README.md) for setup. In short: Python 3.x, packages in
`requirements.txt`, plus the Graphviz system binary for network visualizations.

## Contact

 h.farheen.29402@khi.iba.edu.pk — reach out with questions about methodology, data provenance, or access to anything not included here.
