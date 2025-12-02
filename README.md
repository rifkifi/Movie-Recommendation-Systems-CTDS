# Movie Recommendation Systems – CTDS

## Overview

Three recommendation system approaches: item-based, content-based, and model-based were developed and analyzed to determine the most suitable and effective method for the application. For the item-based recommendation system, the Jaccard similarity algorithm was used to measure the similarity between movies based on their user sets. In the content-based approach, clustering algorithms such as K-means and hierarchical clustering were applied to group similar movies, enabling recommendations based on cluster membership. Lastly, Singular Value Decomposition (SVD) was employed as the model-based method, allowing the system to predict user ratings for specific movies and generate recommendations based on these predicted ratings. Data that is used in this project was collected from TMDB website using its [API](https://developer.themoviedb.org/docs/getting-started).

## Data Notes

- `movies_dataset.csv`: curated metadata (titles, IDs, genres) assembled from TMDB API pulls. Extend it by re‑running the collection cells (requires a TMDB API key).
- `reviews_dataset.csv`: reviews dataset that also curated from TMDB API containing users and their review and rating to a specific movie.

## Repository Structure

```
Project/
└── Movie-Recommendation-Systems-CTDS/
    ├── MovieRec.ipynb          # Main notebook
    ├── movies_dataset.csv      # movies dataset
    ├── reviews_dataset.csv     # Ratings/reviews dataset
    └── requirements.txt        # Python dependencies for the notebook
```

## Environment Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/Movie-Recommendation-Systems-CTDS.git
   cd Movie-Recommendation-Systems-CTDS
   ```
2. **Create your environment** (tested with Python **3.12.9**)
   - **Windows (PowerShell / CMD)**
     ```bash
     python -m venv .venv
     .venv\Scripts\activate
     ```
   - **macOS (or Linux)**
     ```bash
     python3 -m venv .venv
     source .venv/bin/activate
     ```
3. **Install requirements**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

Key libraries: `pandas`, `numpy`, `scikit-learn`, `scipy`, `mlxtend`, `nltk`, `seaborn`, `matplotlib`, `networkx`, `scikit-surprise`, `wordcloud`, and `requests`.

## Usage

1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Open `MovieRec.ipynb`.
3. Run the notebook sequentially. The workflow is already ordered from data acquisition (commented because data has been collected) -> data processing and visualization -> recommendation systems -> evaluation.
4. Working with the recommendation systems
   - **Item-based (Jaccard similarity):** In the `Item-Based Recommendations` section, pick a `movie_id` from `df_movies` and run the `recommend_jaccard_based` function. It returns the top similar titles based on overlapping user sets; increase `k` to see more options.
   - **Content-based clustering:** Use the `Clustering & Content Recommendations` section to rerun the KMeans/Hierarchical cells after adjusting feature engineering or cluster counts. The `recommend_movies` helper function then accepts a username of a reviewer and recommends movies for them.
   - **Model-based (SVD):** Scroll to `SVD Recommendations`, rerun the Surprise `SVD` training cell to generate predicted rating. Then call the `predict_top_n` and specify username of a user to recommend movies.
