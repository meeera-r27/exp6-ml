# Experiment 6 — Naïve Bayes Text Classification

## Objective

To implement and compare **Multinomial Naïve Bayes** and **Bernoulli Naïve Bayes** classifiers for text classification using the **20 Newsgroups dataset**.

---

## Dataset

The experiment uses four categories from the 20 Newsgroups dataset:

- `comp.graphics`
- `rec.sport.hockey`
- `sci.med`
- `talk.politics.mideast`

### Dataset Size

| Dataset | Number of Documents |
|---|---:|
| Training Set | 2342 |
| Testing Set | 1560 |

Headers, footers, and quotations were removed from the documents before processing. :contentReference[oaicite:0]{index=0}

---

## Algorithms Used

### 1. Multinomial Naïve Bayes

Multinomial Naïve Bayes is suitable for text classification using word-frequency or word-count features.

For this experiment:

- `CountVectorizer` is used
- English stop words are removed
- Maximum features = 10,000
- Word-count representation is used
- `alpha = 1.0`

### 2. Bernoulli Naïve Bayes

Bernoulli Naïve Bayes works with binary features representing whether a word is present or absent.

For this experiment:

- `CountVectorizer` is used
- English stop words are removed
- Maximum features = 10,000
- Binary representation is used
- `alpha = 1.0`

The notebook implements both vectorization strategies and trains both classifiers. :contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2}

---

## Methodology

```text
20 Newsgroups Dataset
        ↓
Select 4 Categories
        ↓
Remove Headers, Footers & Quotes
        ↓
Text Preprocessing
        ↓
CountVectorizer
        ↓
 ┌─────────────────────┐
 │                     │
 ↓                     ↓
Word Counts        Binary Features
 │                     │
 ↓                     ↓
Multinomial NB     Bernoulli NB
 │                     │
 └──────────┬──────────┘
            ↓
       Predictions
            ↓
 Accuracy & Macro F1
            ↓
 Classification Report
