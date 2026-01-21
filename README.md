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
| `text_classification_machine_human_arabertv2_test_modified.ipynb` | AraBERTv2   | Evaluation on **modified test data** to analyze robustness. |
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

* Tests effectiveness of **layer freezing** in cross-lingual adaptation.
* Evaluates **multilingual models’ transfer ability** in low-resource scenarios.
* Metrics include **accuracy, precision, recall, F1-score**, and **qualitative error inspection**.

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

## Installation & Requirements

* Python 3.8+
* PyTorch 2.x
* Transformers 4.x
* pandas, numpy, scikit-learn

Install dependencies:

```bash
pip install -r requirements.txt
```

Optional for Jupyter notebooks:

```bash
pip install notebook jupyterlab
```

---

## Usage

### Arabic Classification

1. Open a notebook under `Arabic/`.
2. Preprocess the dataset (scripts are included in the notebook).
3. Train or evaluate using **AraBERTv2, Asafya BERT, or CAMeL BERT**.

### Cross-lingual Experiments

1. Open notebooks under `Cross-lingual/`.
2. Select the transfer direction (Arabic → Urdu or Urdu → Arabic).
3. Run experiments with or without **layer freezing**.

### Urdu Pipelines

1. Open notebooks under `Urdu/`.
2. Train and evaluate **Urdu classification pipelines** using mBERT.

---

## Evaluation Metrics

* **Accuracy** – Overall correctness of predictions.
* **Precision & Recall** – To evaluate false positives and false negatives.
* **F1-score** – Harmonic mean of precision and recall.
* **Error Analysis** – Examine misclassified examples to understand model weaknesses.

---

## Contributing

We welcome contributions for:

* Adding new **models or datasets**.
* Extending **cross-lingual experiments**.
* Improving **evaluation scripts or analysis pipelines**.

---

## Citation

If you use this repository or datasets in your research, please cite the **Ayahverse AbjadGenEval Shared Task**.

