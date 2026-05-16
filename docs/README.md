# Notebooks

This directory contains exploratory, analytical, and visualization notebooks used during the development of the EXIST2026 project.

The notebooks are intended for:
- exploratory data analysis (EDA)
- debugging
- qualitative inspection
- visualization
- error analysis
- interpretability experiments
- reporting support

Production training, evaluation, and inference logic and all the reusable code belong in `src/`.

---

# Directory Structure

<!-- BEGIN TREE -->
```text
└── README.md
```
<!-- END TREE -->

---

# Notebook Categories

## `exploration/`

Contains notebooks for:
- dataset inspection
- label distribution analysis
- exploratory visualizations
- annotator statistics
- sanity checks

These notebooks are typically used during early-stage experimentation and dataset understanding.

Examples:
- class imbalance analysis
- multilingual distribution inspection
- annotation consistency analysis

---

## `analysis/`

Contains notebooks focused on:
- model evaluation
- error analysis
- disagreement analysis
- uncertainty estimation
- calibration studies

These notebooks are typically used after training experiments.

Examples:
- confusion matrix inspection
- false positive analysis
- disagreement-aware evaluation
- confidence calibration plots

---

## `visualization/`

Contains notebooks for:
- embedding visualization
- attention analysis
- multimodal explainability
- qualitative result inspection

Examples:
- t-SNE / UMAP projections
- CLIP attention maps
- token attribution visualizations
- multimodal feature inspection

---

# Guidelines

## Keep notebooks lightweight

Avoid implementing reusable logic directly inside notebooks.

Instead:
- place reusable functionality in `src/`
- import modules into notebooks

Example:

```python
from src.evaluation.metrics import compute_f1
from src.analysis.error_analysis import analyze_errors
```

---

## Naming Convention

Use descriptive filenames with clear scope.

Recommended format:

```text
<topic>_<purpose>.ipynb
```

Examples:

```text
dataset_statistics.ipynb
error_analysis.ipynb
attention_maps.ipynb
```

Avoid names like:

```text
test.ipynb
final.ipynb
new_analysis2.ipynb
```

---

# Reproducibility

Whenever possible:
- fix random seeds
- document experiment IDs
- reference configuration files
- store generated outputs in `outputs/`

Example:

```python
EXPERIMENT_ID = "exp12_clip_annotator"
CONFIG_PATH = "configs/experiments/multimodal/exp12_clip_annotator.yaml"
```

---

# Data Access

Notebooks assume the repository root as the working directory.

Recommended launch command:

```bash
jupyter lab
```

or

```bash
jupyter notebook
```

from the project root.

---

# Output Management

Generated artifacts should NOT be committed directly inside notebooks.

Store outputs in:
- `outputs/reports/`
- `outputs/figures/`
- `outputs/predictions/`

Large generated files should be excluded from version control.

---

# Best Practices

Recommended:
- clear markdown explanations
- small executable sections
- visual summaries
- links to related experiments
- explicit assumptions

Avoid:
- duplicated code
- hidden state dependencies
- long-running training inside notebooks
- manual path hacks
- storing secrets or API keys

---

# Suggested Workflow

Typical workflow:

1. Explore data in `exploration/`
2. Implement reusable code in `src/`
3. Run experiments via `scripts/train.py`
4. Analyze outputs in `analysis/`
5. Generate figures in `visualization/`

---

# Related Directories

| Directory | Purpose |
|---|---|
| `src/` | Reusable project code |
| `scripts/` | Experiment entrypoints |
| `configs/` | Experiment configuration |
| `outputs/` | Generated artifacts |
| `docs/` | Documentation |

---

# Notes

- Notebooks are considered research artifacts, not production pipelines.
- Important findings should eventually be migrated into:
  - `docs/`
  - reusable analysis modules
  - experiment reports
```