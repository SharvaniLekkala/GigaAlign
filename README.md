# GigaAlign — Notebook Guide & Setup README

GigaAlign is a research project focused on **cross-lingual word alignment** across Indian languages using multilingual transformer models.

This README explains:

- What each notebook is about
- How to use each notebook
- Installation requirements
- Access requirements
- Hugging Face authentication
- Required dependencies
- Recommended workflow

---

# Project Overview

This repository contains multiple notebooks that experiment with and benchmark **word alignment models** between:

- English ↔ Hindi
- English ↔ Tamil
- English ↔ Telugu
- English ↔ Malayalam

The notebooks mainly combine:

- **LaBSE** → semantic similarity
- **IndicBERTv2** → structural alignment
- **MuRIL** → multilingual Indian language modeling
- **Awesome-Align**
- **SimAlign**
- **fast_align**

---

# Access Requirements

Before running notebooks, make sure you have access to:

## Recommended Platform
- Google Colab (Recommended)
- Jupyter Notebook
- VS Code Notebook Environment

---

# System Requirements

Recommended:

- Python 3.9+
- RAM: 8GB+
- GPU (recommended for transformer models)
- Internet connection for model downloads

---

# Installation

Install all required dependencies.

## Core Installation

```bash
pip install torch transformers sentence-transformers
pip install datasets huggingface_hub
pip install simalign
pip install scikit-learn numpy pandas scipy matplotlib seaborn
pip install openpyxl
```

---

# Additional Installations

## Awesome-Align

```bash
pip install git+https://github.com/neulab/awesome-align.git
```

---

## fast_align Installation

Required for comparison notebooks.

### Linux / Colab

```bash
apt-get install build-essential cmake
git clone https://github.com/clab/fast_align
cd fast_align
mkdir build
cd build
cmake ..
make
```

---

# Hugging Face Authentication

Some notebooks require Hugging Face access.

---

## Install Hugging Face Hub

```bash
pip install huggingface_hub
```

---

## Login via CLI

```bash
huggingface-cli login
```

Paste your Hugging Face token.

---

## Notebook Login

Add this at the top of notebooks if needed:

```python
from huggingface_hub import login
login(token="YOUR_HF_TOKEN")
```

---

## Get Hugging Face Token

Create free token here:

https://huggingface.co/settings/tokens

---

# Notebook Run Rules

Always follow:

1. Open notebook
2. Run cells from top to bottom
3. Install dependencies first
4. Authenticate HF token if needed
5. Modify input sentences if required
6. Execute evaluation section

---

# Recommended Notebook Learning Order

1. `Sim_vs_Awe.ipynb`
2. `Giga_align (1).ipynb`
3. `HindiTeluguALignment (1).ipynb`
4. `COMBALIGN (2).ipynb`
5. `COMBALIGN_final (1).ipynb`
6. `MuRIL_ground.ipynb`
7. `muril-attempt.ipynb`
8. `Telugufocus (1).ipynb`
9. `hindi_comparisions.ipynb`
10. `tamil_comparisions.ipynb`

---

# Notebook Descriptions

---

## `Giga_align (1).ipynb`

### Purpose
Main English–Tamil alignment notebook.

### What It Does
- Uses LaBSE + IndicBERTv2
- Generates alignment matrix
- Handles many-to-one mappings
- Tamil-focused alignment logic

### How To Use
- Run sequentially
- Provide sentence pairs
- Observe alignment outputs

---

## `CombAlign.ipynb`

### Purpose
First CombAlign prototype.

### What It Does
- Combines:
  - LaBSE
  - Awesome-Align
  - fast_align
- Malayalam dataset experiments

### How To Use
- Requires HF login
- Run dependency cells
- Execute fully

---

## `COMBALIGN (2).ipynb`

### Purpose
Balanced Hindi alignment pipeline.

### What It Does
- Semantic + structural fusion
- Threshold-based alignment
- Rescue orphan words

### How To Use
- Run all cells
- Modify thresholds if needed

---

## `COMBALIGN_final (1).ipynb`

### Purpose
Final reproducible Hindi notebook.

### What It Does
- Cleaned pipeline
- Excel input support
- Final evaluation setup

### How To Use
- Best notebook for final testing
- Replace Excel path if needed

---

## `CombAlignTeluguHindi_shar (1).ipynb`

### Purpose
Strict alignment version.

### What It Does
- High precision
- Lower false positives
- Strict thresholding

### How To Use
- Compare against standard CombAlign
- Precision-focused testing

---

## `HindiTeluguALignment (1).ipynb`

### Purpose
Evaluation notebook.

### What It Does
- Computes:
  - AER
  - Precision
  - Recall
- Uses gold alignments

### How To Use
- Run after alignment generation
- Compare prediction quality

---

## `MuRIL_ground.ipynb`

### Purpose
Fusion optimization notebook.

### What It Does
- Grid-search tuning
- Weight optimization
- Tamil experiments

### How To Use
- Requires HF token
- Run tuning section

---

## `muril-attempt.ipynb`

### Purpose
Earlier MuRIL experiment.

### What It Does
- Hungarian matching
- Ensemble alignment

### How To Use
- Compare architecture evolution

---

## `Sim_vs_Awe.ipynb`

### Purpose
Model comparison notebook.

### What It Does
- SimAlign vs Awesome-Align
- Alignment comparison

### How To Use
- Best starting notebook
- Learn baseline behaviors

---

## `hindi_comparisions.ipynb`

### Purpose
Hindi benchmarking.

### What It Does
Compares:
- SimAlign
- Awesome-Align
- fast_align
- CombAlign

### How To Use
- Run after core notebooks
- Observe metrics

---

## `tamil_comparisions.ipynb`

### Purpose
Tamil benchmark.

### What It Does
- Same benchmark setup
- Uses gold Excel dataset

### How To Use
- Provide Excel file path
- Run entire notebook

---

## `Telugufocus (1).ipynb`

### Purpose
Telugu-specific experiments.

### What It Does
- Many-to-many alignment
- Telugu token handling

### How To Use
- Language-specific testing

---

# Notebook Categories

| Category | Notebooks |
|----------|------------|
| Core Pipeline | Giga_align, COMBALIGN, COMBALIGN_final |
| Comparison | Sim_vs_Awe, hindi_comparisions, tamil_comparisions |
| Evaluation | HindiTeluguALignment |
| Optimization | MuRIL_ground, muril-attempt |
| Language-Specific | Telugufocus |

---

# Recommended Starting Point

If short on time:

1. `Sim_vs_Awe.ipynb`
2. `Giga_align (1).ipynb`
3. `COMBALIGN_final (1).ipynb`

These explain most of the project workflow.

---

# Important Notes

- Large notebooks may not preview properly on GitHub
- Download locally if preview fails
- GPU strongly recommended
- Some notebooks require internet for model downloads
- Transformer models may take time during first run

---
