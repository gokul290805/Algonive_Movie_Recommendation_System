# 🎬 Movie Recommendation System

A hybrid movie recommendation system built using the MovieLens dataset that combines **Content-Based Filtering**, **Collaborative Filtering**, and **Sentiment Analysis** to generate personalized movie recommendations with TMDb poster integration.

---

## 📌 Project Overview

This project was developed as part of the **Algonive Data Science Internship**. It recommends movies based on user preferences, viewing history, and ratings using a hybrid approach that blends multiple recommendation techniques.

---

## 🚀 Features

- **Content-Based Filtering** — Recommends movies with similar genres and tags using TF-IDF and cosine similarity
- **Collaborative Filtering** — Suggests movies based on similar user preferences using sparse matrix and cosine similarity
- **Sentiment Analysis** — Refines recommendations using TextBlob sentiment scores on movie tags
- **Hybrid Recommender** — Blends all three signals (50% content + 30% collaborative + 20% sentiment) into a final score
- **TMDb API Integration** — Fetches live movie posters for visual display
- **Poster Grid Display** — Shows recommendations with posters, genres, and hybrid scores

---

## 🗂️ Dataset

Download the MovieLens dataset from Kaggle:
👉 https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset

Place the CSV files in a `Dataset/` folder:
- movie.csv
- rating.csv
- tag.csv
- link.csv
---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas`, `numpy` | Data manipulation |
| `scikit-learn` | TF-IDF, cosine similarity |
| `scipy` | Sparse matrix (memory optimization) |
| `textblob`, `nltk` | Sentiment analysis |
| `requests` | TMDb API calls |
| `Pillow`, `IPython` | Poster display in notebook |

---

## ⚙️ How It Works

### 1. Content-Based Filtering
- Combines genres and tags into a single content profile per movie
- Applies TF-IDF vectorization to extract 23,000+ features
- Computes cosine similarity across all 27,000+ movies

### 2. Collaborative Filtering
- Filters active users (≥50 ratings) and active movies (≥50 ratings)
- Builds a sparse user-movie matrix using `scipy.csr_matrix` to avoid RAM issues
- Computes user-user cosine similarity and recommends movies liked by similar users

### 3. Sentiment Analysis
- Extracts user tags for each movie from `tag.csv`
- Uses TextBlob to compute sentiment polarity (-1 to +1)
- Higher sentiment score boosts the movie's final hybrid rank

### 4. Hybrid Recommender
```
Hybrid Score = 0.5 × Content Score + 0.3 × Collaborative Score + 0.2 × Sentiment Score
```

---

## 📊 Sample Output

The system displays a **poster grid** with:
- Movie title
- Genres
- Hybrid recommendation score

---

## 🔧 Setup & Installation

1. Clone the repository
```bash
git clone https://github.com/gokul290805/Algonive_Movie_Recommendation_System.git
cd Movie-Recommendation-System
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Download TextBlob corpora
```bash
python -m textblob.download_corpora
```

4. Download the MovieLens dataset from [grouplens.org](https://grouplens.org/datasets/movielens/) and place the CSV files in a `Dataset/` folder

5. Add your TMDb API key in the notebook:
```python
API_KEY = 'your_tmdb_api_key_here'
```

6. Open `Movie_Recommendation_System.ipynb` in VS Code or Jupyter and run all cells

---

## 📁 Project Structure

```
Movie-Recommendation-System/
│
├── Movie_Recommendation_System.ipynb
├── requirements.txt
├── README.md
└── Dataset/
    ├── movie.csv
    ├── rating.csv
    ├── tag.csv
    └── link.csv
```

---

## 👤 Author

**Gokul Krishnan**
- GitHub: [gokul290805](https://github.com/gokul290805)
- LinkedIn: [Gokul Krishnan](https://linkedin.com/posts/gokul-krishnan-615226260)

---

## 🏢 Internship

Developed as part of the **Algonive Data Science Internship**
