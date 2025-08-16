

# Movie Recommender System

This project is a content-based movie recommender system that suggests movies similar to a user's selection. The recommendations are based on the movie's genre, keywords, cast, and crew. The application is built with Python and deployed as a web app using Streamlit.

## Features

-   **Content-Based Recommendations:** Suggests movies based on their content similarity.
-   **Interactive UI:** A user-friendly web interface built with Streamlit that allows users to select a movie from a dropdown menu.
-   **Dynamic Poster Fetching:** Fetches and displays movie posters from The Movie Database (TMDb) API for a visually appealing experience.

## How It Works

The recommender system follows these steps:

1.  **Data Collection:** The project uses the [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata).

2.  **Data Preprocessing:**
    * The movie and credits datasets are merged.
    * Relevant features like `genres`, `keywords`, `overview`, `cast`, and `crew` (director) are extracted.
    * The textual data is cleaned and combined into a single "tags" column for each movie.
    * Natural Language Processing (NLP) techniques like lowercasing and stemming are applied to the tags.

3.  **Feature Extraction:**
    * The text data in the "tags" column is converted into a numerical format using the `CountVectorizer` (Bag of Words model). This creates a vector representation for each movie.

4.  **Similarity Calculation:**
    * The `cosine similarity` is calculated between the vector representations of all the movies to determine their similarity to each other.

5.  **Recommendation:**
    * When a user selects a movie, the system finds the top 5 most similar movies based on the cosine similarity scores and displays them.

