# Relational Laboratory

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23383034.svg)](https://doi.org/10.5281/zenodo.23383034)

An interactive agent-based model of a relational theory of transformation, and the code and data behind the paper
**"Width: How the Range a System Can Hold Shapes Who Connects, Who Leads and Who Closes"** — written by Claude (Anthropic) on the theory of Lolla March, 2026.

**Read the paper:** [Width.pdf](Width.pdf)

**Open the laboratory:** `index.html` — in any browser, or online via GitHub Pages (Settings → Pages → deploy from the main branch).
The interface switches between English and Russian with the button at the bottom.

## What the model is

90 particles move in a field. Each has its own rhythm (its *nature*) and adjusts it to neighbours within reach.
For every pair the model measures how stable their rhythms are together (*coherence*), and each particle accumulates
*experience* with each other particle — positive when the contact coheres, negative (friction) when it does not.
Experience feeds back: it strengthens or weakens coupling and attraction. Groups (*molecules*) are not drawn; they are found.

The paper studies **width**: how much mismatch a particle can hold before contact counts as friction.
Width can be frozen, volatile (fluctuating like anxiety that comes and goes), or living (changed by experience:
processed experience widens, unprocessed friction narrows).

The theory itself is described in *The Space of Becoming* — written by Claude (Anthropic) on the theory of Lolla March, 2026. All model parameters are listed in the paper's appendix.

## Reproducing the paper

Requirements: Node.js (18 or newer) and Python 3 with matplotlib.

```
cd research
node exp1.js spread 1        # one run of Experiment 1; prints one line of JSON
python3 figs.py              # rebuilds all figures from the data in research/data
./run_all.sh                 # re-runs every experiment of the paper (3–4 hours on one core), then rebuilds the figures
```

The scripts read the model directly from `index.html`, so they always use exactly the published laboratory.

| Script | Paper |
|---|---|
| `exp1.js` | Experiment 1 — wide particles become centres |
| `exp2.js` | Experiment 2 — width differences create one-sided relations |
| `exp3.js` | Experiment 3 — volatile width |
| `exp4.js` | Experiments 4 and 5 — living width, two fates, rescue by volatility, equal strengths |
| `exp6.js` | Experiment 6 — robustness |
| `pairs.js` | Who bonds with whom |
| `figs.py` | All figures (`research/figures`) |

`research/data` holds the raw results reported in the paper (model version 1.2), one JSON line per run.
`long_run.json` holds the values from the author's 70-minute live run (Section 7), read from her recordings.

## Model versions

- **1.0** — first experiments.
- **1.1** — fixes a rare undefined value in the noise generator (about once per billion calls) that spread through relations.
- **1.2** — the published version: the world scales as a whole with the screen at constant density; delay history is stored after the safety check; coupling stops growing after 400 units of experience; bilingual interface.

Results were checked on 1.1 and 1.2 (and the first experiments on 1.0); the paper reports 1.2 and gives the earlier values for comparison.
The paper also describes the artefacts found during the work and how they were separated from real behaviour.

## Notes

Some comments in the code are in Russian.

## How to cite

Relational Laboratory: Width and the Structure of Relations (version 1.2). Lolla March; paper written by Claude (Anthropic). Zenodo, 2026. https://doi.org/10.5281/zenodo.23383034

## Authorship and licence

The theory is by Lolla March. The model, the experiments and the analysis were developed together with an AI assistant (Claude, Anthropic);
the author ran the live sessions, found most of the artefacts and decided what counted as a result.

Code: MIT licence (see `LICENSE`). Text, figures and data: CC BY 4.0.
