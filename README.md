### A Lyric-Based Song Recommender Using TF-IDF and Word2Vec
**CS5101 Natural Language Processing** | Semester 2, 2025-2026

---

## Overview

SotGoL (Song that Goes Like) is a lyric-based song recommendation system built
using Natural Language Processing techniques. The system allows a user to input
either a lyric snippet or a set of keywords and emotions, and returns a ranked
list of similar songs from a dataset of tens of thousands of Spotify tracks.

The system follows a complete NLP pipeline covering data loading and exploration,
text preprocessing, feature extraction, recommendation engine development,
visualization and analysis, and an interactive live demo. Two NLP approaches are
implemented and compared: TF-IDF with cosine similarity for surface-level lyric
matching, and Word2Vec with averaged embeddings and cosine similarity for
semantic meaning matching.

---

## Input Modes

| Mode | Description | Example Input |
|---|---|---|
| Lyric Snippet | Paste a line or phrase from a song | "I can't stop the feeling, dancing through the night" |
| Keywords / Mood | Type descriptive words or emotions | "heartbreak tears lonely missing someone" |

---

## Project Structure

```
sotgol/
├── SotGoL.ipynb                  # Main Jupyter Notebook (report + code)
├── spotify_millsongdata.csv      # Spotify Million Song Dataset (see Setup)
└── README.md                     # Project overview and setup guide
```

---

## Setup

### Requirements

- Python 3.8 to 3.12 (Python 3.11 recommended)
- Jupyter Notebook or VS Code with the Jupyter extension

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/CTRL-JUJU/sotgol.git
   cd sotgol
   ```

2. Install the required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn nltk gensim wordcloud
   ```

3. Download the required NLTK resources by running the following in
   Python or in the first code cell of the notebook:
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('punkt_tab')
   nltk.download('stopwords')
   nltk.download('wordnet')
   nltk.download('omw-1.4')
   ```

### Dataset

This project uses the **Spotify Million Song Dataset** available on Kaggle.

1. Download the dataset from:
   https://www.kaggle.com/datasets/notshrirang/spotify-million-song-dataset
2. Place the file `spotify_millsongdata.csv` in the same folder as the notebook.

---

## Usage

1. Open `SotGoL.ipynb` in Jupyter Notebook or VS Code.
2. Make sure `spotify_millsongdata.csv` is in the same folder as the notebook.
3. Run all cells in order from top to bottom using **Run All**.
4. Navigate to **Section 7 (Live Demo)** and interact with the recommender
   using the live input cell.
5. Select an input mode when prompted, enter your lyric snippet or keywords,
   and receive recommendations from both the TF-IDF and Word2Vec pipelines.
6. Type `exit` to end the session.

> To get recommendations outside of the live demo, you can call either
> recommender function directly in any code cell:
> ```python
> recommend_tfidf("your lyric snippet here", top_n=5)
> recommend_w2v("your keywords here", top_n=5)
> ```
> To compare both at once:
> ```python
> compare_recommenders("your input here", top_n=5)
> ```

---
