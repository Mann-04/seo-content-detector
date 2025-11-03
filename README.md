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
## Project Structure

.
├── data/
│   ├── data.csv                  # Input dataset (HTML content)
│   ├── extracted_content.csv     # Parsed titles & body text
│   ├── features.csv              # Engineered features
│   └── duplicates.csv            # Detected duplicates
├── models/
│   ├── tfidf_vectorizer.pkl      # Trained TF-IDF model
│   └── quality_model.pkl         # Trained Random Forest
├── seo_pipeline.ipynb            # Main Jupyter Notebook
├── README.md
├── requirements.txt
└── .gitignore

---

## Installation

```bash
git clone https://github.com/yourusername/seo-content-detector.git
cd seo-content-detector
pip install -r requirements.txt
