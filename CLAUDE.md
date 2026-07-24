# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

This repo holds the Jupyter notebook course materials for **GPGN 436/536 Geophysical Computing**, taught by Dr. Ge Jin and Dr. Jeff Shragge in the Geophysics Department at Colorado School of Mines. There is no application code, build system, package, or test suite — the deliverables are the notebooks themselves, designed to be opened directly in Google Colab.

## Structure

- `NN_Topic.ipynb` — numbered course modules in teaching order (`01_Introduction.ipynb` through `09_Regression.ipynb`). The number prefix determines lecture sequence; keep it when adding or renaming modules.
- `figures/` — static images/GIFs embedded in the notebooks via relative paths (e.g. `figures/2D_Interpolation_intro.png`). If a figure is renamed or moved, update the `<img>`/markdown references in the notebook that uses it.

Each notebook opens with a Colab badge markdown cell linking to `https://colab.research.google.com/github/jinwar/GeophysicsComputingColab/blob/main/<notebook>.ipynb` — when adding a new module notebook, include the same badge pattern pointing at its filename, and a header cell crediting the instructors, matching the existing notebooks.

## Content conventions

- Notebooks mix long-form markdown (course text, LaTeX equations via `$$...$$`) with Python code cells demonstrating the numerical method being taught. Markdown explanation and code are meant to be read together — don't strip or shorten the prose when editing a notebook.
- Code style is instructional/exploratory (course-demo notebooks), not production code: expect inline plotting, `HTML`/`animation` demos, and sympy-based symbolic derivations alongside numpy code. Match this style rather than introducing production-style abstractions.
- Common libraries used across notebooks: `numpy`, `matplotlib.pyplot`, `scipy` (`interpolate`, `integrate`), `sympy`, `pandas`, `IPython.display` (`HTML`, `Image`), `imageio`, `time`. No `requirements.txt` exists; these are assumed to already be available in the Colab/Jupyter environment.
- Kernel/language metadata across all notebooks is `python3`.

## Working with notebooks

- Edit notebooks as `.ipynb` JSON (cell `source` arrays) or via a notebook-aware tool — do not hand-roll raw JSON edits that could corrupt cell structure or outputs.
- There is no automated way to "run the tests" for this repo; the closest equivalent to verification is executing the notebook end-to-end (e.g. `jupyter nbconvert --to notebook --execute <notebook>.ipynb`) to confirm all cells run without error after a change.
- Avoid committing notebooks with large embedded outputs (e.g. big plots/animations) unless that output is the point of the change — it bloats the repo and diffs.
