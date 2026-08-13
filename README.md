# 🎬 Movie Recommender System

> **An end-to-end movie recommendation platform built with Python, TF-IDF, FastAPI, Streamlit, and the TMDB API.**

🔗 **Live Demo:** https://movie-recommender-system-dfbyay3x2d5akgylcpb8dp.streamlit.app/  
🔗 **Backend API:** https://movie-recommender-system-7ufx.onrender.com/docs

---

## 📌 Overview

The **Movie Recommender System** is an end-to-end machine learning application that helps users discover movies based on their interests.

The project combines:

- **Content-based recommendation** using TF-IDF similarity
- **Genre-based recommendations**
- **TMDB API integration** for movie search, posters, metadata, and details
- **FastAPI** for serving the recommendation backend
- **Streamlit** for an interactive user interface
- **Render** for backend deployment
- **Streamlit Community Cloud** for frontend deployment

The goal was not only to build a recommendation model, but to turn it into a **complete, deployable ML application** with a user-friendly interface and production-style API architecture.

---

## ✨ Key Features

### 🔎 Intelligent Movie Search
Search for movies using keywords such as:

- `Avengers`
- `Batman`
- `Love`
- `Harry Potter`

The application provides matching movie suggestions and displays relevant movie cards with posters.

### 🎯 Content-Based Recommendations

The system uses **TF-IDF vectorization and cosine similarity** to identify movies with similar textual content.

The recommendation pipeline is based on movie information such as:

- Movie title
- Overview
- Genres
- Other available textual metadata

### 🎭 Genre-Based Recommendations

Users can also discover movies with similar genres, providing an additional recommendation strategy when TF-IDF recommendations are unavailable or insufficient.

### 🏠 Movie Discovery Feed

The home page provides different movie categories:

- 🔥 Trending
- ⭐ Popular
- 🏆 Top Rated
- 🎬 Now Playing
- 📅 Upcoming

### 📄 Movie Details

Selecting a movie opens a detailed page containing:

- Movie title
- Poster
- Backdrop
- Release date
- Genres
- Overview
- Similar movie recommendations

### 🌐 TMDB Integration

The application uses the **TMDB API** to retrieve current movie information, including search results, movie details, posters, and other metadata.

### ⚡ FastAPI Backend

The recommendation logic and API functionality are exposed through a FastAPI backend with documented REST endpoints.

### 🎨 Streamlit Frontend

The Streamlit interface provides an interactive experience with:

- Search
- Autocomplete suggestions
- Movie grids
- Movie details
- Recommendation sections
- Category selection
- Responsive grid controls

---

## 🧠 Recommendation Approach

The project primarily follows a **content-based filtering** approach.

### 1. Text Processing

Movie textual information is prepared and combined to create a meaningful representation of each movie.

### 2. TF-IDF Vectorization

The textual representation is converted into numerical vectors using **TF-IDF (Term Frequency–Inverse Document Frequency)**.

TF-IDF gives higher importance to words that are useful for distinguishing one movie from another.

### 3. Cosine Similarity

Cosine similarity is then used to measure how similar two movie vectors are.

Conceptually:

```text
Movie A
   ↓
Text Features
   ↓
TF-IDF Vector
   ↓
Cosine Similarity
   ↓
Most Similar Movies
```

### 4. Genre-Based Filtering

A second recommendation strategy uses movie genres to identify movies with similar genre characteristics.

### 5. Combined User Experience

The application exposes both approaches through the API and presents the recommendations through the Streamlit interface.

---

## 🏗️ System Architecture

```text
                    ┌───────────────────────┐
                    │        User           │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │   Streamlit Frontend  │
                    │       app.py          │
                    └───────────┬───────────┘
                                │
                         HTTP Requests
                                │
                                ▼
                    ┌───────────────────────┐
                    │     FastAPI Backend   │
                    │       main.py         │
                    └───────┬───────┬───────┘
                            │       │
                ┌───────────┘       └────────────┐
                ▼                                ▼
      ┌──────────────────┐             ┌──────────────────┐
      │ Recommendation   │             │     TMDB API     │
      │ Engine           │             │ Movie Metadata   │
      │ TF-IDF + Genre   │             └──────────────────┘
      └────────┬─────────┘
               │
               ▼
      ┌──────────────────┐
      │ Movie Results /  │
      │ Recommendations  │
      └────────┬─────────┘
               │
               ▼
      ┌──────────────────┐
      │ Streamlit UI     │
      └──────────────────┘
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python** | Core development |
| **Pandas** | Data processing |
| **NumPy** | Numerical operations |
| **Scikit-learn** | TF-IDF & cosine similarity |
| **FastAPI** | Backend REST API |
| **Uvicorn** | ASGI server |
| **Streamlit** | Interactive frontend |
| **TMDB API** | Movie metadata and search |
| **Requests / HTTPX** | API communication |
| **Pickle** | Persisting trained recommendation artifacts |
| **Git & GitHub** | Version control |
| **Render** | FastAPI deployment |
| **Streamlit Community Cloud** | Frontend deployment |

---

## 🔌 API Endpoints

The FastAPI backend currently exposes endpoints including:

| Method | Endpoint | Purpose |
|---|---|---|
| `GET` | `/health` | Health check |
| `GET` | `/home` | Movie home feed |
| `GET` | `/tmdb/search` | Search movies using TMDB |
| `GET` | `/movie/id/{tmdb_id}` | Get movie details |
| `GET` | `/movie/search` | Search/recommendation bundle |
| `GET` | `/recommend/genre` | Genre-based recommendations |
| `GET` | `/recommend/tfidf` | TF-IDF-based recommendations |

### Interactive API Documentation

The FastAPI Swagger documentation is available here:

**https://movie-recommender-system-7ufx.onrender.com/docs**

---

## 🖥️ Application Flow

### Home Page

```text
User enters keyword
        ↓
TMDB Search API
        ↓
Matching movie suggestions
        ↓
Movie cards with posters
        ↓
User selects a movie
        ↓
Movie Details
        ↓
TF-IDF + Genre Recommendations
```

### Movie Recommendation Flow

```text
Movie Overview / Metadata
          ↓
     Text Processing
          ↓
      TF-IDF Matrix
          ↓
   Cosine Similarity
          ↓
 Similar Movie Ranking
          ↓
 Top-N Recommendations
```

---

## 🚀 Deployment

The application is deployed using a two-service architecture.

### Frontend

**Streamlit Community Cloud**

🔗 https://movie-recommender-system-dfbyay3x2d5akgylcpb8dp.streamlit.app/

### Backend

**Render**

🔗 https://movie-recommender-system-7ufx.onrender.com

This separation allows the frontend and backend to be developed and deployed independently.

---

## ⚙️ Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/Satyamsoni07/Movie-Recommender-system.git
cd Movie-Recommender-system
```

### 2. Create a virtual environment

#### Windows

```powershell
python -m venv .venv
.venv\Scripts\activate
```

#### macOS / Linux

```bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the TMDB API key

Create a `.env` file:

```env
TMDB_API_KEY=your_tmdb_api_key
```

Do **not** commit your `.env` file or API key to GitHub.

### 5. Start the FastAPI backend

```bash
uvicorn main:app --reload
```

The backend will normally be available at:

```text
http://127.0.0.1:8000
```

Swagger documentation:

```text
http://127.0.0.1:8000/docs
```

### 6. Start Streamlit

In another terminal:

```bash
streamlit run app.py
```

The Streamlit application will open in your browser.

---

## 🔐 Environment Variables

The project uses environment variables for sensitive configuration.

Example:

```env
TMDB_API_KEY=your_api_key
```

For deployment, the API key should be stored in the hosting platform's environment variables rather than hard-coded in the source code.

---

## 📂 Project Structure

```text
Movie-Recommender-system/
│
├── app.py                         # Streamlit frontend
├── main.py                        # FastAPI backend
├── requirements.txt               # Python dependencies
├── .env                           # Local secrets (not committed)
│
├── models / artifacts              # Saved recommendation artifacts
│   └── ...
│
└── README.md
```

> The exact model/artifact filenames may vary depending on the project version.

---

## 📊 What I Learned From This Project

This project helped bring together multiple parts of the machine learning lifecycle:

- Data preprocessing
- Feature engineering
- Natural Language Processing
- TF-IDF vectorization
- Cosine similarity
- Content-based recommendation
- REST API development
- API integration
- Frontend development
- Environment variable management
- Model/artifact persistence
- Git and GitHub
- Cloud deployment
- Debugging production deployment issues

More importantly, it demonstrates the transition from a **notebook/model-level project to a usable end-to-end ML application**.

---

## 🔮 Future Improvements

Potential improvements include:

- User-personalized recommendations based on watch history
- Hybrid recommendation combining content and collaborative filtering
- Better ranking using multiple similarity signals
- Recommendation explanations such as *"Recommended because you liked..."*
- User ratings and feedback
- Authentication and user profiles
- Recommendation evaluation using appropriate ranking metrics
- Improved caching and response times
- Automated testing and CI/CD
- Containerization with Docker

---

## 👨‍💻 Author

**Satyam Soni**

MS in Artificial Intelligence & Data Science  
ABV-IIITM Gwalior

### Connect

- GitHub: https://github.com/Satyamsoni07
- Project: https://github.com/Satyamsoni07/Movie-Recommender-system

---

## ⭐ Project Links

| Resource | Link |
|---|---|
| 🎬 **Live Demo** | https://movie-recommender-system-dfbyay3x2d5akgylcpb8dp.streamlit.app/ |
| ⚡ **API Documentation** | https://movie-recommender-system-7ufx.onrender.com/docs |
| 💻 **GitHub Repository** | https://github.com/Satyamsoni07/Movie-Recommender-system |

---

## 📜 Disclaimer

Movie information and media metadata are provided through the TMDB API. This project is intended for educational and portfolio purposes.
