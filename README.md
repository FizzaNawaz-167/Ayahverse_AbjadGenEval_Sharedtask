# Ayahverse_AbjadGenEval_Sharedtask

**Overview:**
This repository contains the code, datasets, and notebooks used for the ArabicGenEval Shared Task, focusing on evaluating Arabic and cross-lingual (Arabic-Urdu) text classification and generation models. The tasks include identifying machine-generated vs human-written text and exploring cross-lingual transfer with multilingual models.

## Directories
### Arabic

Contains notebooks for Arabic text classification using various pretrained models:

AraBERTv2 – Standard and modified test notebooks.

Asafya BERT – Alternative Arabic BERT model.

CAMeL BERT – Another baseline for comparison.

### Urdu

Contains Urdu classification pipelines using mBERT.

### Cross-lingual

Notebooks for cross-lingual text classification and transfer experiments between Arabic and Urdu:

Experiments with freezing vs non-freezing layers.

mBERT-based transfer for both directions (Arabic ↔ Urdu).

### Datasets

Contains all data used in experiments:

ground_truth.csv – Labeled Arabic dataset for evaluation.

urdu_train.csv – Urdu training dataset for cross-lingual experiments.

final_test_unlabeled.csv – Test set for evaluation.

by_polishing-00000-of-00001.parquet – Preprocessed dataset for large-scale experiments.
