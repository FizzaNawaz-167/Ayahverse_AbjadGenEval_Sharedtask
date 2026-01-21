# Ayahverse_AbjadGenEval_Sharedtask

## Overview

This repository contains the code, datasets, and notebooks used for the **ArabicGenEval Shared Task**, now under the Ayahverse project umbrella. The task focuses on evaluating **Arabic text generation and classification systems**, with an emphasis on:

* Identifying **machine-generated vs human-written text**.
* Exploring **cross-lingual transfer** between Arabic and Urdu using multilingual models like **mBERT**.
* Providing a **reproducible framework** for benchmarking models on Arabic text generation tasks.

The repository includes **pretrained models, datasets, and evaluation pipelines** to facilitate experiments in both monolingual and cross-lingual settings.

---

## Repository Structure

```
.
├─ Arabic/
├─ Urdu/
├─ Cross-lingual/
├─ Datasets/
└─ README.md
```

---

## Directories and Notebooks

### Arabic

Contains notebooks for **Arabic text classification** using different pretrained models:

| Notebook                                                          | Model       | Purpose                                                     |
| ----------------------------------------------------------------- | ----------- | ----------------------------------------------------------- |
| `text_classification_machine_human_arabertv2.ipynb`               | AraBERTv2   | Baseline Arabic classification using standard test data.    |
| `text_classification_machine_human_arabertv2_test_modified.ipynb` | AraBERTv2   | Evaluation on test data, uses **modified** AraBERTv2 architecture for better performance. |
| `text_classification_machine_human_asafya_bert.ipynb`             | Asafya BERT | Alternative Arabic BERT model for comparison.               |
| `text_classification_machine_human_camelbert.ipynb`               | CAMeL BERT  | Another Arabic BERT baseline for benchmarking.              |

**Features:**

* Preprocessing includes **normalization and tokenization** consistent with model requirements.
* Evaluation includes **accuracy, precision, recall, and F1-score**.
* Includes **error analysis** for misclassified examples.

---

### Urdu

Contains notebooks for **Urdu text classification** using **mBERT**:

| Notebook                     | Purpose                             |
| ---------------------------- | ----------------------------------- |
| `urdu_pipelineC_mbert.ipynb` | Pipeline C for Urdu classification. |
| `urdu_pipelineD_mbert.ipynb` | Pipeline D for Urdu classification. |

**Notes:**

* Helps compare **monolingual Urdu performance** against cross-lingual Arabic knowledge transfer.
* Includes full **training, evaluation, and metric calculation** pipelines.

---

### Cross-lingual

Notebooks for **cross-lingual experiments** between Arabic and Urdu:

| Notebook                                       | Purpose                                                   |
| ---------------------------------------------- | --------------------------------------------------------- |
| `arabic_to_urdu_freezing_layers.ipynb`         | Arabic → Urdu transfer with **frozen layers**.            |
| `arabic_to_urdu_without_freezing_layers.ipynb` | Same transfer **without freezing layers** for comparison. |
| `urdu_to_arabic_freezing_layers.ipynb`         | Urdu → Arabic transfer with frozen layers.                |
| `urdu_to_arabic_mbert.ipynb`                   | Full **mBERT cross-lingual transfer** without freezing.   |
| `urdu_to_arabic_without_freezing_layers.ipynb` | Urdu → Arabic transfer **without freezing layers**.       |

**Highlights:**

* It uses the `text_classification_machine_human_arabertv2.ipynb` file which implements the basic model.
* Tests effects of **layer freezing** in cross-lingual adaptation.
* Evaluates **multilingual models’ transfer ability** in low-resource scenarios.
* Metrics include **accuracy, precision, recall, F1-score**, and **qualitative error inspection**.
* Graphically shows the adaptation.
---

### Datasets

Contains all **raw and preprocessed datasets** used in experiments:

| File                                  | Description                                                   |
| ------------------------------------- | ------------------------------------------------------------- |
| `ground_truth.csv`                    | Labeled Arabic dataset for **evaluation and benchmarking**.   |
| `urdu_train.csv`                      | Urdu training dataset for **cross-lingual experiments**.      |
| `final_test_unlabeled.csv`            | Unlabeled test set used for **final evaluation submissions**. |
| `by_polishing-00000-of-00001.parquet` | Preprocessed dataset for **large-scale experiments**.         |

**Preprocessing Notes:**

* Arabic text normalization preserves **punctuation**, compatible with models like AraBERTv2.
* Urdu text is **tokenized and normalized** for mBERT pipelines.
* Ensures **consistent input formatting** across experiments for reproducibility.

---

## Evaluation Metrics

* **Accuracy** – Overall correctness of predictions.
* **Precision & Recall** – To evaluate false positives and false negatives.
* **F1-score** – Harmonic mean of precision and recall.
* **Error Analysis** – Examine misclassified examples to understand model weaknesses.

---

## Citation

If you use this repository or datasets in your research, please cite the **Ayahverse AbjadGenEval Shared Task**.

