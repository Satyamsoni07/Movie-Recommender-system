# 🎬 Movie Recommender System
### AI-Powered Movie Discovery Platform | Content-Based ML + Full-Stack Deployment

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-Streamlit-FF4B4B?style=for-the-badge)](https://movie-recommender-system-dfbyay3x2d5akgylcpb8dp.streamlit.app/)
[![API Docs](https://img.shields.io/badge/⚡_API_Docs-FastAPI-009688?style=for-the-badge)](https://movie-recommender-system-7ufx.onrender.com/docs)
[![GitHub](https://img.shields.io/badge/💻_Source-GitHub-181717?style=for-the-badge)](https://github.com/Satyamsoni07/Movie-Recommender-system)

---

## 💡 Why This Project Matters

A production-grade, **end-to-end machine learning application** — not a notebook, not a toy demo. This project takes a recommendation model from raw data all the way to a **live, publicly deployed product** with a decoupled API backend and interactive frontend, mirroring how ML systems are actually shipped in industry.

**Try it now → [Live App](https://movie-recommender-system-dfbyay3x2d5akgylcpb8dp.streamlit.app/) | [API Docs](https://movie-recommender-system-7ufx.onrender.com/docs)**

---

## 🏆 Highlights at a Glance

| | |
|---|---|
| 🧠 **ML Engineering** | TF-IDF vectorization + cosine similarity for content-based recommendations |
| ⚡ **Backend Engineering** | Production REST API built with FastAPI, fully documented via Swagger |
| 🎨 **Frontend Engineering** | Interactive, responsive Streamlit UI with live search & recommendations |
| 🌐 **Third-Party Integration** | Real-time data from the TMDB API (search, posters, metadata) |
| ☁️ **Cloud Deployment** | Independently deployed frontend (Streamlit Cloud) & backend (Render) |
| 🔐 **Security Practices** | Environment-variable-based secrets management, no hardcoded keys |

---

## ⚙️ Tech Stack

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white"/>
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white"/>
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white"/>
<img src="https://img.shields.io/badge/Render-46E3B7?style=flat&logo=render&logoColor=white"/>
<img src="https://img.shields.io/badge/TMDB_API-01B4E4?style=flat&logo=themoviedatabase&logoColor=white"/>
</p>

---

## 🧠 The ML Pipeline

A content-based recommendation engine built from scratch using classic, well-understood NLP techniques — chosen deliberately for interpretability and low-latency inference in production.

```text
Movie Metadata (title, overview, genres)
              ↓
        Text Preprocessing
              ↓
       TF-IDF Vectorization
              ↓
       Cosine Similarity Matrix
              ↓
     Ranked Similar Movies (Top-N)
```

**Two complementary recommendation strategies:**
- **Content-based (TF-IDF):** captures nuanced textual similarity across plot and metadata
- **Genre-based fallback:** ensures robust recommendations even on sparse data

---

## 🏗️ System Architecture

Designed with a clean **separation of concerns** — decoupled frontend/backend, independently deployable and scalable.

```text
        User
          │
          ▼
 ┌──────────────────┐
 │ Streamlit Frontend │
 └────────┬──────────┘
          │  REST calls
          ▼
 ┌──────────────────┐        ┌──────────────────┐
 │  FastAPI Backend  │ ─────▶ │     TMDB API      │
 └────────┬──────────┘        └──────────────────┘
          │
          ▼
 ┌──────────────────────────┐
 │ TF-IDF + Genre Engine     │
 └────────┬──────────────────┘
          ▼
   Ranked Recommendations
          ▼
     Back to User (UI)
```

---

## 🔌 API — Built for Real Consumption

A fully documented, testable REST API — not just internal glue code.

| Method | Endpoint | Purpose |
|---|---|---|
| `GET` | `/health` | Health check |
| `GET` | `/home` | Curated home feed (Trending, Popular, Top Rated...) |
| `GET` | `/tmdb/search` | Real-time movie search via TMDB |
| `GET` | `/movie/id/{tmdb_id}` | Rich movie detail lookup |
| `GET` | `/movie/search` | Combined search + recommendation bundle |
| `GET` | `/recommend/genre` | Genre-based recommendations |
| `GET` | `/recommend/tfidf` | ML-driven TF-IDF recommendations |

📄 **[Explore the interactive Swagger docs →](https://movie-recommender-system-7ufx.onrender.com/docs)**

---

## ✨ Product Features

- 🔎 **Smart search** with autocomplete across a full movie catalog
- 🎯 **Personalized recommendations** via two blended similarity strategies
- 🏠 **Curated discovery feed** — Trending, Popular, Top Rated, Now Playing, Upcoming
- 📄 **Rich movie detail pages** with posters, backdrops, and related titles
- 📱 **Responsive UI** built for a smooth browsing experience

---

## 🚀 Live Deployment

| Layer | Platform | Link |
|---|---|---|
| Frontend | Streamlit Community Cloud | [Launch App →](https://movie-recommender-system-dfbyay3x2d5akgylcpb8dp.streamlit.app/) |
| Backend | Render | [View API →](https://movie-recommender-system-7ufx.onrender.com/docs) |

Deployed as two independently scalable services — reflecting real-world microservice-style architecture rather than a monolithic script.

---

## 👨‍💻 About the Author

**Satyam Soni**
MS in Artificial Intelligence & Data Science — ABV-IIITM Gwalior

Building full-stack ML products end-to-end: from model design to deployed, user-facing applications.

📫 [GitHub — @Satyamsoni07](https://github.com/Satyamsoni07)

---

⭐ **If this project caught your eye, a star on the repo is always appreciated!**
[github.com/Satyamsoni07/Movie-Recommender-system](https://github.com/Satyamsoni07/Movie-Recommender-system)
