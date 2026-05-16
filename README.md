# EXIST 2026

This repository contains the project materials, codebase, and experiments developed for the **EXIST 2026 shared task**, focusing on applied NLP and machine learning methods for classification and evaluation of text-based data.

The project is designed to be modular, reproducible, and easy to extend for experimenting with different model architectures and training strategies.



## Overview

The main goal of this project is to build robust NLP models for the EXIST 2026 task, including:

- Data preprocessing and cleaning
- Model training and fine-tuning
- Evaluation using standard classification metrics
- Experiment tracking and result analysis

The repository supports both traditional machine learning baselines and transformer-based models.


## Repository Structure

```text
EXIST2026/
│
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── pyproject.toml
├── setup.py
│
├── configs/
│   │
│   ├── tasks/
│   │   ├── majority.yaml
│   │   ├── annotator.yaml
│   │   ├── soft_labels.yaml
│   │   └── disagreement_subset.yaml
│   │
│   ├── models/
│   │   │
│   │   ├── text/
│   │   │   ├── deberta_v3.yaml
│   │   │   ├── roberta.yaml
│   │   │   └── xlm_roberta.yaml
│   │   │
│   │   ├── multimodal/
│   │   │   ├── clip_latefusion.yaml
│   │   │   ├── clip_earlyfusion.yaml
│   │   │   ├── llava.yaml
│   │   │   └── qwen_vl.yaml
│   │   │
│   │   └── ensemble/
│   │       └── voting.yaml
│   │
│   ├── training/
│   │   ├── default.yaml
│   │   ├── large_gpu.yaml
│   │   ├── debug.yaml
│   │   └── seed42.yaml
│   │
│   ├── losses/
│   │   ├── cross_entropy.yaml
│   │   ├── focal.yaml
│   │   ├── kl_divergence.yaml
│   │   └── annotator_aware.yaml
│   │
│   └── experiments/
│       │
│       ├── text/
│       │   ├── exp01_deberta_majority.yaml
│       │   ├── exp02_deberta_softlabels.yaml
│       │   └── exp03_xlmr_annotator.yaml
│       │
│       ├── multimodal/
│       │   ├── exp10_clip_majority.yaml
│       │   ├── exp11_clip_softlabels.yaml
│       │   ├── exp12_clip_annotator.yaml
│       │   └── exp13_llava_softlabels.yaml
│       │
│       └── ensemble/
│           └── exp20_voting.yaml
│
├── data/
│   │
│   ├── raw/
│   │   │
│   │   ├── train/
│   │   │   ├── images/
│   │   │   └── annotations.csv
│   │   │
│   │   ├── dev/
│   │   └── test/
│   │
│   ├── interim/
│   │   ├── cleaned/
│   │   ├── ocr/
│   │   └── translated/
│   │
│   ├── processed/
│   │   │
│   │   ├── majority_vote/
│   │   │   ├── train.csv
│   │   │   ├── dev.csv
│   │   │   └── test.csv
│   │   │
│   │   ├── annotator_level/
│   │   │   ├── train.csv
│   │   │   ├── dev.csv
│   │   │   └── test.csv
│   │   │
│   │   ├── soft_labels/
│   │   │   ├── train.csv
│   │   │   └── dev.csv
│   │   │
│   │   └── disagreement_subset/
│   │       ├── train.csv
│   │       └── dev.csv
│   │
│   └── metadata/
│       ├── annotators.csv
│       ├── label_mapping.json
│       └── dataset_statistics.json
│
├── src/
│   │
│   ├── data/
│   │   │
│   │   ├── preprocessing.py
│   │   ├── splits.py
│   │   ├── collators.py
│   │   ├── augmentations.py
│   │   │
│   │   ├── datasets/
│   │   │   ├── majority_dataset.py
│   │   │   ├── annotator_dataset.py
│   │   │   ├── softlabel_dataset.py
│   │   │   └── multimodal_dataset.py
│   │   │
│   │   └── loaders/
│   │       ├── image_loader.py
│   │       ├── text_loader.py
│   │       └── multimodal_loader.py
│   │
│   ├── models/
│   │   │
│   │   ├── text/
│   │   │   ├── deberta_classifier.py
│   │   │   ├── roberta_classifier.py
│   │   │   └── xlmr_classifier.py
│   │   │
│   │   ├── multimodal/
│   │   │   ├── clip_latefusion.py
│   │   │   ├── clip_earlyfusion.py
│   │   │   ├── llava_classifier.py
│   │   │   └── qwen_vl_classifier.py
│   │   │
│   │   ├── ensemble/
│   │   │   └── voting_ensemble.py
│   │   │
│   │   └── common/
│   │       ├── pooling.py
│   │       ├── fusion.py
│   │       └── heads.py
│   │
│   ├── tasks/
│   │   ├── majority_task.py
│   │   ├── annotator_task.py
│   │   ├── softlabel_task.py
│   │   └── disagreement_task.py
│   │
│   ├── training/
│   │   ├── trainer.py
│   │   ├── optimizer.py
│   │   ├── scheduler.py
│   │   ├── callbacks.py
│   │   ├── checkpointing.py
│   │   └── distributed.py
│   │
│   ├── losses/
│   │   ├── cross_entropy.py
│   │   ├── focal_loss.py
│   │   ├── kl_divergence.py
│   │   └── annotator_aware_loss.py
│   │
│   ├── evaluation/
│   │   ├── metrics.py
│   │   ├── evaluator.py
│   │   ├── calibration.py
│   │   └── disagreement_metrics.py
│   │
│   ├── inference/
│   │   ├── predict.py
│   │   ├── ensemble_predict.py
│   │   └── submission.py
│   │
│   ├── analysis/
│   │   ├── agreement_analysis.py
│   │   ├── error_analysis.py
│   │   ├── uncertainty_analysis.py
│   │   └── explainability.py
│   │
│   └── utils/
│       ├── logging.py
│       ├── io.py
│       ├── seed.py
│       ├── registry.py
│       ├── config.py
│       └── constants.py
│
├── scripts/
│   │
│   ├── prepare_data.py
│   ├── build_soft_labels.py
│   ├── compute_agreement.py
│   │
│   ├── train.py
│   ├── evaluate.py
│   ├── predict.py
│   ├── generate_submission.py
│   │
│   └── run_experiment.sh
│
├── notebooks/
│   │
│   ├── exploration/
│   │   ├── dataset_statistics.ipynb
│   │   ├── label_distribution.ipynb
│   │   └── annotator_behavior.ipynb
│   │
│   ├── analysis/
│   │   ├── error_analysis.ipynb
│   │   ├── disagreement_analysis.ipynb
│   │   └── calibration_analysis.ipynb
│   │
│   └── visualization/
│       ├── attention_maps.ipynb
│       └── embedding_visualization.ipynb
│
├── outputs/
│   │
│   ├── checkpoints/
│   │   ├── exp01/
│   │   ├── exp02/
│   │   └── exp10/
│   │
│   ├── logs/
│   │   ├── tensorboard/
│   │   └── wandb/
│   │
│   ├── predictions/
│   │   ├── exp01_dev.csv
│   │   └── exp10_test.csv
│   │
│   ├── submissions/
│   │   ├── submission_v1.csv
│   │   └── submission_final.csv
│   │
│   └── reports/
│       ├── metrics.json
│       └── confusion_matrices/
│
├── docs/
│   │
│   ├── repository_structure.md
│   ├── datasets.md
│   ├── experiments.md
│   ├── models.md
│   ├── training.md
│   ├── evaluation.md
│   └── reproducibility.md
│
├── tests/
│   ├── test_datasets.py
│   ├── test_models.py
│   ├── test_losses.py
│   └── test_metrics.py
│
└── assets/
    ├── figures/
    ├── tables/
    └── diagrams/
```