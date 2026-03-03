
# 🎬 Movie Recommendation System (ML + Streamlit)

A smart **Movie Recommendation System** built using **Machine Learning, NLP**, and **Streamlit**.  
It analyzes movie metadata—such as genres, keywords, cast, crew, and overview—and recommends the **Top 5 most similar movies** using **Cosine Similarity**.
This project uses the **TMDB 5000 Movies Dataset** and stores preprocessed data in `.pkl` files for fast, real-time recommendations.

---

## 🚀 Features

- ✔️ Content-based movie recommendation  
- ✔️ Movie similarity computed using **Cosine Similarity**  
- ✔️ Uses metadata: genres, keywords, cast, crew, overview  
- ✔️ Clean and interactive **Streamlit UI**  
- ✔️ Fast predictions using pre-saved `movie_list.pkl` and `similarity.pkl`  
- ✔️ End-to-end ML project with preprocessing + UI  

---

## 📁 Folder Structure


movie-recommendation/
│── app.py # Streamlit frontend
│── movie.py # Model training + preprocessing
│── movie_list.pkl # Preprocessed movie metadata
│── similarity.pkl # Similarity matrix (cosine similarity)
│── tmdb_5000_movies.csv # Dataset
│── tmdb_5000_credits.csv # Dataset
│── .gitignore
│── README.md


---

## 🧠 How it Works (Short Technical Overview)

1. **movie.py**
   - Loads the TMDB datasets  
   - Extracts genres, keywords, cast, crew  
   - Converts JSON-like strings into lists  
   - Cleans, merges, and creates a **tags** column  
   - Vectorizes using `CountVectorizer (5000 features)`  
   - Computes **cosine similarity matrix**  
   - Saves results as:
     - `movie_list.pkl`
     - `similarity.pkl`

2. **app.py**
   - Loads the pickle files  
   - Displays movie list in a Streamlit dropdown  
   - Recommends top 5 movies based on similarity score  

---

## 🛠️ Requirements

Install the dependencies:

```bash
pip install streamlit scikit-learn pandas numpy pillow
▶️ Running the Project
1. Train the Model

(Only needed once)

python movie.py
This generates:
movie_list.pkl
similarity.pkl
2. Start the Streamlit App
streamlit run app.py
The app will open in your browser automatically.

🎯 Example Output

When you select a movie (e.g., Avatar), the system returns 5 similar movies such as:

The Avengers
Guardians of the Galaxy
Star Trek
Prometheus
The Matrix

📊 Architecture Diagram (Text-Based)
                     ┌───────────────────────────┐
                     │     TMDB Movie Dataset     │
                     └─────────────┬─────────────┘
                                   │
                                   ▼
                       ┌──────────────────────┐
                       │   movie.py (ML)      │
                       │ - Preprocessing       │
                       │ - Vectorization       │
                       │ - Cosine Similarity   │
                       └─────────┬────────────┘
                                 │ generates
                                 ▼
                   ┌─────────────────────────────┐
                   │ movie_list.pkl               │
                   │ similarity.pkl               │
                   └─────────┬───────────────────┘
                             │ loads
                             ▼
                  ┌─────────────────────────────┐
                  │        Streamlit UI         │
                  │          app.py             │
                  └─────────┬───────────────────┘
                            │
                            ▼
                ┌─────────────────────────────────┐
                │  Top 5 Movie Recommendations     │
