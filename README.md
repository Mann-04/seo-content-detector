# SEO Content Quality & Duplicate Detector

![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/pandas-2.0%2B-green)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.3%2B-orange)
![License: MIT](https://img.shields.io/badge/license-MIT-purple)

A **machine learning pipeline** to analyze web content for **SEO quality scoring** and **near-duplicate detection** using **TF-IDF**, **cosine similarity**, and **Random Forest classification**.

Built as a **Data Science Assignment** for **AI/ML Engineer** role.

---

## Features

- **HTML Parsing** from pre-scraped content
- **Text Preprocessing** & **NLP Feature Engineering**
- **TF-IDF Embeddings** for semantic similarity
- **Duplicate Detection** with cosine similarity (>0.80)
- **Thin Content Flagging** (<500 words)
- **Content Quality Scoring** using Random Forest
- **Real-time URL Analysis** via command-line input
- **Saved Models & Vectorizers** for production use

---

## Installation

```bash
git clone https://github.com/yourusername/seo-content-detector
cd seo-content-detector
pip install -r requirements.txt
jupyter notebook notebooks/seo_pipeline.ipynb
```

## Quick Start

- Download dataset
Kaggle Primary → Save as data/data.csv
- Run the notebook
  -Execute all cells → Generates:
    - data/extracted_content.csv
    - data/features.csv
    - data/duplicates.csv
    - models/tfidf_vectorizer.pkl & quality_model.pkl


## Real-time analysis
```
url = input("Enter URL: ")
result = analyze_url(url)
print(result)
```

## Key Decisions
- Libraries: BeautifulSoup (robust HTML parsing), scikit-learn (TF-IDF + Random Forest), nltk (readability & tokenization) — lightweight, no heavy dependencies.
- HTML Parsing: Used "p, article, main tags" → captures main content, skips nav/footer noise.
- Similarity Threshold = 0.80: Balances precision/recall — catches near-duplicates without flagging minor overlaps.
- Random Forest over Logistic Regression: Handles non-linear patterns in word count, readability, and sentence complexity.

## Results Summary
- Model Accuracy: 90% | F1 Score: 0.67,0.96,0.83 (High/Low/Medium classes)
- Duplicates Found: 2 (>80% similarity)
- Thin page Content: 18 (26.09%)
- Top Features:
  1. flesch_reading_ease (importance: 0.48)
  2. word_count (importance: 0.28)
  3. sentence_count (importance: 0.24)
- Word Cloud:
<img width="790" height="405" alt="image" src="https://github.com/user-attachments/assets/e741d108-84a7-4a29-a4d4-9219238fe989" />


## Limitations
- Relies on pre-scraped HTML — no live crawling fallback.
- TF-IDF misses semantic nuance (e.g., synonyms) — could upgrade to BERT.
- Quality labels are rule-based — needs human-labeled data for production.
