# ReviewSense AI

AI-powered NLP pipeline that transforms **50,000+ Amazon reviews** into smart product recommendations using **Sentiment Analysis, Semantic Clustering, and Generative AI**.

---

# Overview

ReviewSense AI combines multiple NLP and AI models into one end-to-end review analysis system.

The project automatically:

- Classifies customer sentiment
- Groups similar products into semantic categories
- Generates AI-powered recommendation articles
- Identifies top products and common complaints

Goal:

> “Stop reading thousands of reviews. Let AI summarize them for you.”

---

# Features

- DistilBERT sentiment classification
- Semantic product clustering using embeddings
- AI-generated buying recommendations
- Automatic complaint extraction
- Product ranking per category
- Cluster visualization with PCA
- Word clouds for cluster interpretation

---

# Pipeline Architecture

## 1. Sentiment Analysis — DistilBERT

Classifies reviews into:

- Positive
- Neutral
- Negative

Why DistilBERT?

- Lightweight transformer model
- Fast training and inference
- Strong contextual understanding
- High accuracy for NLP classification tasks

### Performance

| Metric | Score |
|---|---|
| Accuracy | 0.953 |
| Precision | 0.946 |
| Recall | 0.953 |
| F1-score | 0.948 |

Evaluation methods:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## 2. Semantic Product Clustering — MiniLM + KMeans

Reviews were transformed into embeddings using:

- `SentenceTransformers`
- `all-MiniLM-L6-v2`

Then grouped using:

- `KMeans Clustering`

### Goal

Reduce thousands of product reviews into a few semantic product groups.

### Example Clusters

- Tablets & Multimedia Devices
- Kindle & Reading Devices
- Batteries & Power Products
- Smart Home & Alexa Devices
- Casual/Gift Devices

### Evaluation

- Silhouette Score: ~0.07
- PCA visualization
- Word clouds
- Manual semantic inspection

Why the score is low:

Text reviews often share similar vocabulary, making perfect cluster separation difficult.  
Despite this, semantic themes were clearly visible during qualitative evaluation.

---

## 3. Generative AI Recommendation System

Generative AI was used to create:

- Recommendation articles
- Product summaries
- Complaint analysis
- Buying recommendations

### Input

- Sentiment analysis results
- Cluster insights
- Top-rated products
- Common complaints

### Output

Readable AI-generated recommendation articles per category.

---

# Dataset

Amazon Reviews Dataset containing:

- Product names
- Ratings
- Customer reviews
- Product metadata

Dataset size:

- 50,000+ reviews

---

# Text Preprocessing

The review text was cleaned by:

- Removing punctuation
- Removing special characters
- Removing line breaks
- Standardizing formatting

This improved model consistency and embedding quality.

---

# Technologies Used

## NLP & Machine Learning

- Python
- PyTorch
- Hugging Face Transformers
- SentenceTransformers
- Scikit-learn

## Models

- Logistic Regression TF-IDF
- DistilBERT 
- all-MiniLM-L6-v2
- KMeans
- Qwen 1.5B
- FLAN-T5 Small
- GPT 3.5

## Visualization

- Matplotlib
- WordCloud
- PCA

## Data Processing

- Pandas
- NumPy

---

# Project Structure

```bash
ReviewSenseAI/
│
├── articles_pdf/
│   └── AI-Generated Product Recommendation Articles
│
├── csv_files/
│   └── clean_reviews.csv
│
├── notebooks/
│   ├── 01_merge_and_clean.ipynb
│   ├── 02_classifier.ipynb
│   ├── 03_clustering.ipynb
│   ├── 04_summarization.ipynb
│   └── 05_gpt_product_recommendation_generation
│
├── .gitignore
└── README.md

---



# Running the Project

Open and run the notebooks in order:

```bash
01_preprocessing.ipynb
02_distilbert_classifier.ipynb
03_clustering.ipynb
04_summarization.ipynb
05_gpt_product_recommendation_generation
```

The final notebook generates:

- Product clusters
- Evaluation results
- AI-generated recommendation articles

---

# Example Output

The system generates:

- Top products per category
- Common customer complaints
- Best overall recommendations
- AI-generated buying articles

Example:

> “The All-New Fire HD 8 Tablet stands out as a top performer thanks to its display quality, usability, and strong customer feedback.”

---

# Key Takeaways

- Multi-model NLP pipelines can automate large-scale review analysis
- Semantic embeddings help organize unstructured review data
- Generative AI can convert raw customer feedback into actionable insights
- The system is scalable and adaptable to different datasets and industries

---

# Future Improvements

- Fine-tune clustering quality
- Improve recommendation generation
- Support real-time review analysis
- Integrate larger LLMs

---

# Author

Dimitrios Gretsistas  
AI Engineer Bootcamp Project
