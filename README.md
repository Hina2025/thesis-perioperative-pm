# Perioperative Process Mining Thesis

<!-- TODO: replace with your actual thesis title and a 2-3 sentence abstract. -->
Process mining and analysis of perioperative (surgical) case data — discovering process
flows (heuristics miner / DFG), Bayesian process maps, and surgery duration patterns by
location, surgery type, and surgeon.

This repo is the research handover package: code, outputs, and documentation needed for
a research assistant to pick up the work.

## Repo structure

```
.
├── docs/            Final thesis PDF and defense slides
├── notebooks/       Analysis notebooks (Python / Jupyter)
├── data/            Dataset (encrypted — see data/README.md before doing anything else)
└── figures/
    ├── bar_charts/      Average surgery time bar charts, by location/surgery type
    └── process_maps/    Process mining outputs (frequency nets, time nets, Bayesian nets)
```

## Getting started

1. Read [`HANDOVER.md`](HANDOVER.md) first — it has project status, known issues, and next steps.
2. Read [`data/README.md`](data/README.md) — the dataset is encrypted and requires a
   passphrase shared out-of-band. **Do not skip this.**
3. Set up the environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate        # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   ```

   `graphviz` (the Python package) also needs the Graphviz system binary installed
   separately for network visualizations to render:
   - Windows: `winget install Graphviz.Graphviz` (or download from graphviz.org)
   - macOS: `brew install graphviz`
   - Linux: `apt install graphviz`

4. Decrypt the dataset (instructions in `data/README.md`), then launch Jupyter from the
   `notebooks/` folder so relative paths resolve correctly:

   ```bash
   jupyter notebook
   ```

## Notebooks

- `notebooks/Final_Working.ipynb` — main pipeline: data cleaning, process mining
  (heuristics miner, DFG), surgery duration bar charts by location/surgery type/surgeon.
- `notebooks/beysian.ipynb` — Bayesian process map construction.

## Data sensitivity

The source dataset contains real, patient-level perioperative records (dates of birth,
exact procedure timestamps, city/area, surgeon identifiers). Treat it as protected health
information. See [`data/README.md`](data/README.md) for handling rules before doing
anything with it — including sharing derived outputs.
