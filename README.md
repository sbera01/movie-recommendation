# Movie Recommendation System using NLP, TF-IDF & FastAPI

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit)](https://movie-recommendation-pro.streamlit.app/)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.36.0-FF4B4B?style=for-the-badge&logo=streamlit)](https://streamlit.io/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.111.0-009688?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)

> **Discover your next favorite movie with AI-powered recommendations**

[🚀 **Live Demo**](https://movie-recommendation-pro.streamlit.app/)

---

## 🌟 Overview

This is a movie recommendation system that helps you find similar movies based on what you've watched. I built this using Natural Language Processing (NLP) and TF-IDF (Term Frequency-Inverse Document Frequency) to analyze movie descriptions and find patterns. When you select a movie, the system reads through thousands of movie descriptions and suggests ones that are most similar in terms of plot, themes, and genres.

The project combines machine learning with a real-time web interface - the backend API processes the data and runs the recommendation algorithms, while the frontend provides an easy-to-use search and browse experience.

### What Makes This Project Unique?

- **Built from Scratch**: Implemented NLP pipeline including text cleaning, vectorization, and similarity calculations
- **Real Data Processing**: Gathered and cleaned movie data, handled missing values and inconsistencies
- **Smart Recommendations**: Uses mathematical similarity (Cosine Similarity) to find related movies
- **Full-Stack Implementation**: Created both the ML backend (FastAPI) and user interface (Streamlit)
- **Live & Deployed**: Not just code - it's a working application that anyone can use

---

## ✨ Key Features

### 🔍 Smart Search
- **Instant Results**: Fast search with keyword matching
- **Rich Movie Cards**: Visual poster grids with hover effects

### 🎯 AI-Powered Recommendations
- **TF-IDF Based Similarity**: Content-based filtering using movie descriptions and metadata
- **Genre-Based Matching**: Find similar movies by genre preferences
- **Hybrid Approach**: Combines multiple algorithms for better accuracy

### 🎨 Modern Interface
- **Responsive Design**: Works seamlessly on desktop and mobile
- **Beautiful Gradients**: Modern purple-blue color scheme
- **Smooth Animations**: Hover effects and transitions
- **Dark Theme**: Easy on the eyes

---

## 🚀 Live Demo

**Access the live application here:** [https://movie-recommendation-pro.streamlit.app/](https://movie-recommendation-pro.streamlit.app/)

### How to Use:
1. **Search**: Type a movie name in the search bar
2. **Select**: Choose from autocomplete suggestions or browse results
3. **Explore**: Click "Open" to view detailed information
4. **Discover**: Get personalized recommendations based on your selection

---

## 🛠️ Tech Stack

### Frontend
- **Streamlit** `1.36.0` - Interactive web application framework
- **HTML/CSS** - Custom styling with modern gradients and animations
- **JavaScript** - Dynamic interactions (embedded in Streamlit)

### Backend
- **FastAPI** `0.111.0` - High-performance REST API framework
- **Uvicorn** `0.30.1` - ASGI server for FastAPI
- **Python** `3.11+` - Core programming language

### Machine Learning & Data Processing
- **Scikit-learn** `1.5.1` - For TF-IDF vectorization and Cosine Similarity calculations
- **Pandas** `2.2.2` - For data cleaning and manipulation
- **NumPy** `2.0.1` - For mathematical operations
- **SciPy** `1.13.1` - For computing similarity scores

### External APIs
- **TMDB API** - The Movie Database for comprehensive movie data
- **HTTPX** `0.27.0` - Async HTTP client for API requests

### Deployment
- **Streamlit Cloud** - Frontend hosting
- **Render** - Backend API hosting

---

## 🔬 How I Built This - Step by Step

### Step 1: Data Gathering & Cleaning

**What I Did**:
- Collected movie data from TMDB (The Movie Database) API
- Gathered movie titles, descriptions (overviews), genres, release dates, and poster images
- Cleaned the text data by removing special characters, handling missing descriptions
- Filtered out movies with incomplete information
- Organized data into a structured format for processing

**Why This Matters**: Real-world data is messy. Learning to clean and prepare data is essential for any machine learning project.

### Step 2: Natural Language Processing (NLP)

**Text Processing Steps**:
1. **Lowercasing**: Converted all text to lowercase for consistency
2. **Tokenization**: Split movie descriptions into individual words
3. **Stop Words Removal**: Removed common words like "the", "is", "and" that don't add meaning
4. **Text Combination**: Combined movie titles, overviews, and genres into one text field
5. **Preprocessing**: Prepared clean text ready for vectorization

**Example**: 
- Original: "The Dark Knight is an action thriller..."
- Processed: "dark knight action thriller batman gotham..."

### Step 3: TF-IDF Vectorization

TF-IDF stands for Term Frequency-Inverse Document Frequency. It's a way to convert text into numbers so computers can understand and compare them.

**How It Works**:
- **Term Frequency (TF)**: How often a word appears in a movie description
- **Inverse Document Frequency (IDF)**: How unique that word is across all movies
- **Result**: Words that are common in one movie but rare overall get higher scores

**Implementation**:
- Used Scikit-learn's TfidfVectorizer
- Created a matrix where each movie is represented by numbers
- Each number represents how important each word is for that movie

### Step 4: Cosine Similarity Calculation

Cosine Similarity measures how similar two movies are based on their TF-IDF vectors. It gives a score between 0 and 1:
- **1.0** = Identical movies
- **0.8-0.9** = Very similar
- **0.5-0.7** = Somewhat similar
- **Below 0.5** = Not very similar

**How I Used It**:
1. When you select a movie, I get its TF-IDF vector
2. Compare it with all other movies using Cosine Similarity
3. Sort movies by similarity score
4. Return the top 10-12 most similar movies

**Math Made Simple**: Imagine each movie as an arrow in space. Cosine Similarity checks if two arrows point in the same direction - similar direction means similar movies.

### Step 5: Building the API

**Creating the Backend**:
- Built a REST API using FastAPI (Python framework)
- Created endpoints for search, movie details, and recommendations
- Implemented caching to make responses faster
- Integrated TMDB API for real-time movie data
- Deployed the API on Render for 24/7 availability

**API Features**:
- Handles search queries and returns matching movies
- Processes recommendation requests using TF-IDF model
- Provides genre-based filtering as an alternative method
- Returns movie details with posters and metadata

### Step 6: Creating the User Interface

**Frontend Development**:
- Built with Streamlit (Python web framework)
- Designed modern UI with gradients and smooth animations
- Added real-time search with autocomplete suggestions
- Implemented responsive layout that works on all devices
- Deployed on Streamlit Cloud for public access

**User Experience**:
- Simple search interface - just type a movie name
- Visual movie cards with posters
- Detailed movie information page
- Instant recommendations when you click any movie

---

## ⚙️ System Architecture

### How Everything Works Together

```
User's Browser
      ↓
[Streamlit Frontend] ← What you see and interact with
      ↓
[FastAPI Backend] ← Processes your requests
      ↓
[TF-IDF Model + TMDB API] ← Finds similar movies
      ↓
[Results] ← Sends recommendations back to you
```

### What Happens When You Search:

1. **You Type**: Enter a movie name in the search box
2. **Frontend Sends Request**: Streamlit app sends your query to the FastAPI backend
3. **Backend Searches**: API searches for matching movies in TMDB database
4. **Shows Results**: You see a grid of movies with posters
5. **You Click a Movie**: Select any movie to see details
6. **ML Processing**: TF-IDF model calculates similar movies using Cosine Similarity
7. **Get Recommendations**: Backend returns 10-12 similar movies
8. **Display**: Frontend shows recommendations in a nice grid format

---

## 🔌 API Documentation

### Base URL
```
https://movie-recommendation-mru9.onrender.com
```

### Endpoints

#### 1. Search Movies
```http
GET /tmdb/search
```
**Parameters**:
- `query` (string, required): Search keyword

**Response**: List of movies with posters and metadata

#### 2. Get Movie Details
```http
GET /movie/id/{tmdb_id}
```
**Parameters**:
- `tmdb_id` (integer, required): TMDB movie ID

**Response**: Complete movie information

#### 3. Get Recommendations
```http
GET /movie/search
```
**Parameters**:
- `query` (string, required): Movie title
- `tfidf_top_n` (integer, optional): Number of TF-IDF results
- `genre_limit` (integer, optional): Number of genre-based results

**Response**: Combined recommendations from both algorithms

#### 4. Get Home Feed
```http
GET /home
```
**Parameters**:
- `category` (string, required): trending/popular/top_rated/now_playing/upcoming
- `limit` (integer, optional): Number of results

**Response**: Movies for the selected category

---

## 🎯 What I Learned & Accomplished

✅ **Natural Language Processing**: Implemented text cleaning, tokenization, and preprocessing  
✅ **TF-IDF Implementation**: Built vectorization pipeline from scratch using Scikit-learn  
✅ **Cosine Similarity**: Applied mathematical similarity measures to find related content  
✅ **API Development**: Created RESTful API with FastAPI and proper endpoint design  
✅ **Full-Stack Development**: Built both backend (Python) and frontend (Streamlit)  
✅ **Data Integration**: Connected to external APIs and handled real-time data  
✅ **Deployment**: Successfully deployed on cloud platforms (Render + Streamlit Cloud)  
✅ **Problem Solving**: Handled data cleaning, missing values, and performance optimization  

---

## 👤 Contact

**Your Name**

- 📧 Email: sbera987654321@gmail.com
- 💼 LinkedIn: [linkedin.com/in/sourav-bera-50232b328/](https://www.linkedin.com/in/sourav-bera-50232b328/)
- 🌐 Portfolio: [souravbera.in](https://www.souravbera.in)

---

## 🙏 Acknowledgments

- **TMDB** - The Movie Database for providing comprehensive movie data
- **Streamlit** - For the amazing web framework
- **FastAPI** - For high-performance API development
- **Scikit-learn** - For machine learning tools
- **Render & Streamlit Cloud** - For reliable hosting services

---

## 📊 Project Statistics

- **Languages**: Python, HTML, CSS
- **Lines of Code**: 500+
- **API Endpoints**: 4+
- **ML Models**: 2 (TF-IDF + Genre-based)
- **External APIs**: TMDB
- **Deployment**: Streamlit Cloud + Render

---

<div align="center">

### ⭐ Star this repository if you found it helpful!

**Made with ❤️ and Python**

</div>
