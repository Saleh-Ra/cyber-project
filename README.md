# Phishing Detection — Critical Reproduction Study

**Course:** Data Science in Cyber  
**Student:** Saleh

Reproduction and critical evaluation of:

> Shahrivari, V., Darabi, M. M., & Izadi, M. (2020). *Phishing Detection Using Machine Learning Techniques.* arXiv:2009.11116.

---

## Project description

This project reproduces and critically evaluates a published phishing-detection study that compares multiple machine learning classifiers on the UCI Phishing Websites dataset.

Work includes:

- Reproducing the authors' notebook from their [GitHub repository](https://github.com/fafal-abnir/phishing_detection)
- An independent analysis in `project.ipynb` (EDA, improved CV pipeline, model comparison, error analysis)
- A written report (`report.pdf`) covering summary, critical evaluation, reproducibility, and conclusions

---

## Selected article

- **Paper (PDF):** https://arxiv.org/pdf/2009.11116v1.pdf
- **arXiv abstract:** https://arxiv.org/abs/2009.11116

---

## Original authors' repository

https://github.com/fafal-abnir/phishing_detection

---

## Dataset source

- **UCI Phishing Websites dataset** (Mohammad, Thabtah & McCluskey, 2015)  
  https://archive.ics.uci.edu/dataset/327/phishing+websites
- **Dataset as used in this project** (from the authors' repository):  
  https://github.com/fafal-abnir/phishing_detection/blob/master/dataset.csv
- **Local copy in this repo:** `data/dataset.csv` (11,055 rows, 30 features + label)

Labels: `-1` = phishing, `1` = legitimate.

---

## Repository layout

```
cyber-project/
├── project.ipynb          # Main notebook (EDA, models, evaluation)
├── report.pdf             # Written report
├── requirements.txt       # Python dependencies
└── data/
    └── dataset.csv
```

---

## Execution instructions

### 1. Requirements

- Python 3.10+ (tested with 3.12)
- pip

### 2. Install dependencies

From the project root:

```bash
pip install -r requirements.txt
```

### 3. Run the main notebook

```bash
jupyter notebook project.ipynb
```

Or open `project.ipynb` in PyCharm / VS Code and **Run All** cells top to bottom.

The notebook expects `data/dataset.csv` relative to the project root.

### 4. (Optional) Reproduce the authors' notebook

Clone their repository separately:

```bash
git clone https://github.com/fafal-abnir/phishing_detection.git
cd phishing_detection
pip install xgboost lightgbm catboost
jupyter notebook All_Classifair.ipynb
```

Note: newer XGBoost requires labels `{0, 1}` — map with `y_binary = ((y + 1) // 2).astype(int)` before the XGBoost cell. See report §4 for full reproducibility notes.

