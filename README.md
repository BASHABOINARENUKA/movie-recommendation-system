
🎬 Movie Recommendation System (Content-Based Filtering)

This is a Content-Based Movie Recommendation System built using Python, Machine Learning, and Streamlit.
It recommends movies based on similarity of:

Genres

Keywords

Cast

Crew

Overview (description)

The system analyzes text features and uses Cosine Similarity to find movies similar to the one the user selects.

🚀 Tech Stack Used
Python Libraries

pandas

numpy

scikit-learn

ast

pickle

streamlit

ML / NLP Models Used

CountVectorizer → Converts movie tags into numerical vectors

Cosine Similarity → Finds similar movies based on vector distance

📚 Why Two Datasets Are Used?

This project uses two TMDB datasets:

tmdb_5000_movies.csv

contains: title, overview, genres, keywords

tmdb_5000_credits.csv

contains: cast, crew, director info

These combined features help produce more accurate recommendations.

🧠 How the ML Model Works

Read both CSV files

Merge them using the title column

Extract important features:

Overview

Genres

Keywords

Cast (top 3 actors)

Director

Clean and preprocess the text

Create a combined tags column

Convert tags to vectors using CountVectorizer

Compute Cosine Similarity among all movies

Save processed data as:

movie_list.pkl

similarity.pkl

These pickle files allow fast recommendations.

🧩 Project Structure
ML/
│── app.py                 → Streamlit UI
│── movie.py               → Preprocessing + model training
│── tmdb_5000_movies.csv   → Dataset
│── tmdb_5000_credits.csv  → Dataset
│── movie_list.pkl         → Processed movie list
│── similarity.pkl         → Similarity matrix (ignored in Git)
│── .gitignore             → Prevent large files from pushing
🌐 Streamlit Web App

app.py launches a simple UI:

User selects a movie

The system recommends top 5 similar movies

Run the app using:

streamlit run app.py
⚙️ How to Train the Model

Training is done through:

python movie.py

It generates:

movie_list.pkl

similarity.pkl

These files are used by Streamlit.
