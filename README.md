# Movie Recommendation Systems – CTDS

## Overview

Three recommendation system approaches: item-based, content-based, and model-based were developed and analyzed to determine the most suitable and effective method for the application. For the item-based recommendation system, the Jaccard similarity algorithm was used to measure the similarity between movies based on their user sets. In the content-based approach, clustering algorithms such as K-means and hierarchical clustering were applied to group similar movies, enabling recommendations based on cluster membership. Lastly, Singular Value Decomposition (SVD) was employed as the model-based method, allowing the system to predict user ratings for specific movies and generate recommendations based on these predicted ratings. Data that is used in this project was collected from TMDB website using its API.

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

1. **Create your environment**
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # PowerShell / CMD on Windows
   source .venv/bin/activate  # macOS / Linux
   ```
2. **Install requirements**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

Key libraries: `pandas`, `numpy`, `scikit-learn`, `scipy`, `mlxtend`, `nltk`, `seaborn`, `matplotlib`, `networkx`, `scikit-surprise`, `wordcloud`, and `requests`.

## Usage

1. Launch Jupyter Lab or Notebook:
   ```bash
   jupyter lab
   # or
   jupyter notebook
   ```
2. Open `MovieRec.ipynb`.
3. Run the notebook sequentially. The workflow is already ordered from data acquisition (commented because data has been collected) -> data processing and visualization -> recommendation systems -> evaluation.

## Data Notes

- `movies_dataset.csv`: curated metadata (titles, IDs, genres) assembled from TMDB API pulls. Extend it by re‑running the collection cells (requires a TMDB API key).
- `reviews_dataset.csv`: reviews dataset that also curated from TMDB API containing users and their review and rating to a specific movie.
