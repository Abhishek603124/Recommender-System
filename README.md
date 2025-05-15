# Movie Recommender System

This project implements a content-based movie recommender system using metadata from the TMDB (The Movie Database) dataset. The system recommends movies based on similarity of tags generated from movie genres, keywords, cast, and crew information.

---

## Features

- Data merging and cleaning of TMDB movies and credits datasets
- Extraction and processing of relevant features:
  - Genres
  - Keywords
  - Cast (top 3 actors)
  - Crew (director)
- Text preprocessing including tokenization, lowercasing, and stemming
- Creation of combined tags from multiple metadata fields
- Vectorization of text data using `CountVectorizer`
- Similarity calculation between movies using cosine similarity
- Movie recommendations based on closest matching tags

---

## Tech Stack

- Python 3
- Libraries:
  - pandas
  - numpy
  - scikit-learn (CountVectorizer, cosine_similarity)
  - nltk (PorterStemmer)
  
---

## Dataset

- TMDB 5000 Movies and Credits datasets available from Kaggle:  
  [TMDB Movie Metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

---

## How It Works

1. **Data Preparation**  
   The movies and credits datasets are merged on the movie title.

2. **Feature Extraction**  
   Relevant columns (`genres`, `keywords`, `cast`, `crew`, and `overview`) are extracted and processed. The cast and crew fields are parsed to get the top 3 actors and the director's name respectively.

3. **Tag Creation**  
   The extracted metadata fields are combined into a single text field called `tags`. This forms the basis of similarity comparison.

4. **Text Processing**  
   The tags are converted to lowercase and stemmed using NLTK’s PorterStemmer to normalize the text.

5. **Vectorization and Similarity**  
   The tags are converted to numeric vectors using `CountVectorizer`. Cosine similarity is computed between all movie vectors to find the most similar movies.

6. **Recommendation**  
   Given a movie title, the system finds the closest movies based on cosine similarity scores.

---

## Usage

- To recommend movies similar to a given movie, call:
  ```python
  recommend('Movie Title')
