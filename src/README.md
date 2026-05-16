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
├── evaluation
│   ├── PyEvALL
│   │   ├── .settings
│   │   │   └── org.eclipse.core.resources.prefs
│   │   ├── build
│   │   │   └── lib
│   │   │       └── pyevall
│   │   │           ├── comparators
│   │   │           │   ├── __init__.py
│   │   │           │   ├── comparators.py
│   │   │           │   └── formats.py
│   │   │           ├── metrics
│   │   │           │   ├── __init__.py
│   │   │           │   ├── metricfactory.py
│   │   │           │   └── metrics.py
│   │   │           ├── reports
│   │   │           │   ├── __init__.py
│   │   │           │   └── reports.py
│   │   │           ├── utils
│   │   │           │   └── utils.py
│   │   │           ├── __init__.py
│   │   │           └── evaluation.py
│   │   ├── dist
│   │   │   ├── PyEvALL-0.1.52.tar.gz
│   │   │   ├── PyEvALL-0.1.54.tar.gz
│   │   │   ├── PyEvALL-0.1.56.tar.gz
│   │   │   ├── PyEvALL-0.1.60.tar.gz
│   │   │   ├── PyEvALL-0.1.62.tar.gz
│   │   │   ├── PyEvALL-0.1.63.tar.gz
│   │   │   ├── PyEvALL-0.1.68.tar.gz
│   │   │   ├── PyEvALL-0.1.70.tar.gz
│   │   │   ├── PyEvALL-0.1.71.tar.gz
│   │   │   ├── PyEvALL-0.1.72.tar.gz
│   │   │   ├── PyEvALL-0.1.74.tar.gz
│   │   │   ├── PyEvALL-0.1.76.tar.gz
│   │   │   └── pyevall-0.1.78.tar.gz
│   │   ├── img
│   │   ├── pyevall
│   │   │   ├── comparators
│   │   │   │   ├── __init__.py
│   │   │   │   ├── comparators.py
│   │   │   │   └── formats.py
│   │   │   ├── metrics
│   │   │   │   ├── __init__.py
│   │   │   │   ├── metricfactory.py
│   │   │   │   └── metrics.py
│   │   │   ├── reports
│   │   │   │   ├── __init__.py
│   │   │   │   └── reports.py
│   │   │   ├── utils
│   │   │   │   ├── file.conf
│   │   │   │   ├── pyevall_keys_texts_reports.rep
│   │   │   │   └── utils.py
│   │   │   ├── __init__.py
│   │   │   └── evaluation.py
│   │   ├── PyEvall.egg-info
│   │   │   ├── dependency_links.txt
│   │   │   ├── PKG-INFO
│   │   │   ├── requires.txt
│   │   │   ├── SOURCES.txt
│   │   │   └── top_level.txt
│   │   ├── test
│   │   │   ├── resources
│   │   │   │   ├── format
│   │   │   │   │   ├── duplicated_values
│   │   │   │   │   │   ├── GOLD1.txt
│   │   │   │   │   │   └── SYS1.txt
│   │   │   │   │   ├── json
│   │   │   │   │   │   ├── EMPTY
│   │   │   │   │   │   ├── GOLD_MONO.json
│   │   │   │   │   │   ├── GOLD_MULTI.txt
│   │   │   │   │   │   ├── INCORRECT.json
│   │   │   │   │   │   ├── SCHEMA_INCORRECT.json
│   │   │   │   │   │   ├── SYS2.txt
│   │   │   │   │   │   ├── SYS_DUPLICATE_IDS.json
│   │   │   │   │   │   └── SYS_MONO.json
│   │   │   │   │   └── json_vs_tsv
│   │   │   │   │       ├── GOLD1.txt
│   │   │   │   │       └── SYS1.txt
│   │   │   │   └── metric
│   │   │   │       ├── double_imp
│   │   │   │       │   ├── classification
│   │   │   │       │   │   └── Double_imp_2.txt
│   │   │   │       │   └── ranking
│   │   │   │       │       ├── SYS1.txt
│   │   │   │       │       ├── SYS10.txt
│   │   │   │       │       ├── SYS11.txt
│   │   │   │       │       ├── SYS12.txt
│   │   │   │       │       ├── SYS13.txt
│   │   │   │       │       ├── SYS14.txt
│   │   │   │       │       ├── SYS15.txt
│   │   │   │       │       ├── SYS2.txt
│   │   │   │       │       ├── SYS3.txt
│   │   │   │       │       ├── SYS5.txt
│   │   │   │       │       ├── SYS6.txt
│   │   │   │       │       ├── SYS7.txt
│   │   │   │       │       ├── SYS8.txt
│   │   │   │       │       └── SYS9.txt
│   │   │   │       └── test
│   │   │   │           ├── classification
│   │   │   │           │   ├── gold
│   │   │   │           │   │   └── 1
│   │   │   │           │   │       ├── GOLD1.txt
│   │   │   │           │   │       ├── GOLD10.txt
│   │   │   │           │   │       ├── GOLD11.txt
│   │   │   │           │   │       ├── GOLD12.txt
│   │   │   │           │   │       ├── GOLD13.txt
│   │   │   │           │   │       ├── GOLD14.txt
│   │   │   │           │   │       ├── GOLD15.txt
│   │   │   │           │   │       ├── GOLD16.txt
│   │   │   │           │   │       ├── GOLD17.txt
│   │   │   │           │   │       ├── GOLD18.txt
│   │   │   │           │   │       ├── GOLD19.txt
│   │   │   │           │   │       ├── GOLD2.txt
│   │   │   │           │   │       ├── GOLD20.txt
│   │   │   │           │   │       ├── GOLD21.txt
│   │   │   │           │   │       ├── GOLD22.txt
│   │   │   │           │   │       ├── GOLD23.txt
│   │   │   │           │   │       ├── GOLD24.txt
│   │   │   │           │   │       ├── GOLD25.txt
│   │   │   │           │   │       ├── GOLD3.txt
│   │   │   │           │   │       ├── GOLD4.txt
│   │   │   │           │   │       ├── GOLD5.txt
│   │   │   │           │   │       ├── GOLD6.txt
│   │   │   │           │   │       ├── GOLD7.txt
│   │   │   │           │   │       ├── GOLD8.txt
│   │   │   │           │   │       └── GOLD9.txt
│   │   │   │           │   └── predictions
│   │   │   │           │       └── 1
│   │   │   │           │           ├── SYS1.txt
│   │   │   │           │           ├── SYS10.txt
│   │   │   │           │           ├── SYS11.txt
│   │   │   │           │           ├── SYS12.txt
│   │   │   │           │           ├── SYS13.txt
│   │   │   │           │           ├── SYS14.txt
│   │   │   │           │           ├── SYS15.txt
│   │   │   │           │           ├── SYS16.txt
│   │   │   │           │           ├── SYS17.txt
│   │   │   │           │           ├── SYS18.txt
│   │   │   │           │           ├── SYS19.txt
│   │   │   │           │           ├── SYS2.txt
│   │   │   │           │           ├── SYS20.txt
│   │   │   │           │           ├── SYS21.txt
│   │   │   │           │           ├── SYS22.txt
│   │   │   │           │           ├── SYS23.txt
│   │   │   │           │           ├── SYS24.txt
│   │   │   │           │           ├── SYS25.txt
│   │   │   │           │           ├── SYS3.txt
│   │   │   │           │           ├── SYS4.txt
│   │   │   │           │           ├── SYS5.txt
│   │   │   │           │           ├── SYS6.txt
│   │   │   │           │           ├── SYS7.txt
│   │   │   │           │           ├── SYS8.txt
│   │   │   │           │           └── SYS9.txt
│   │   │   │           └── ranking
│   │   │   │               ├── gold
│   │   │   │               │   ├── GOLD1.txt
│   │   │   │               │   ├── GOLD10.txt
│   │   │   │               │   ├── GOLD11.txt
│   │   │   │               │   ├── GOLD12.txt
│   │   │   │               │   ├── GOLD13.txt
│   │   │   │               │   ├── GOLD14.txt
│   │   │   │               │   ├── GOLD15.txt
│   │   │   │               │   ├── GOLD2.txt
│   │   │   │               │   ├── GOLD3.txt
│   │   │   │               │   ├── GOLD5.txt
│   │   │   │               │   ├── GOLD6.txt
│   │   │   │               │   ├── GOLD7.txt
│   │   │   │               │   ├── GOLD8.txt
│   │   │   │               │   └── GOLD9.txt
│   │   │   │               └── predictions
│   │   │   │                   ├── SYS1.txt
│   │   │   │                   ├── SYS10.txt
│   │   │   │                   ├── SYS11.txt
│   │   │   │                   ├── SYS12.txt
│   │   │   │                   ├── SYS13.txt
│   │   │   │                   ├── SYS14.txt
│   │   │   │                   ├── SYS15.txt
│   │   │   │                   ├── SYS2.txt
│   │   │   │                   ├── SYS3.txt
│   │   │   │                   ├── SYS5.txt
│   │   │   │                   ├── SYS6.txt
│   │   │   │                   ├── SYS7.txt
│   │   │   │                   ├── SYS8.txt
│   │   │   │                   └── SYS9.txt
│   │   │   ├── testformats.py
│   │   │   └── testmetrics.py
│   │   ├── .project
│   │   ├── .pydevproject
│   │   ├── MANIFEST.in
│   │   ├── README.md
│   │   ├── requirements.txt
│   │   └── setup.py
│   └── exist2025_format_val_V0.2.py
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