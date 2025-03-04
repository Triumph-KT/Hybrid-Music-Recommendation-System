# Million Song Recommendation System Using Rank-Based and Collaborative Filtering

Developed a hybrid music recommendation system to suggest songs based on user preferences and global popularity, leveraging Rank-Based and User-User Collaborative Filtering techniques to enhance user engagement on large-scale music platforms.

## Project Overview

This project focuses on building a music recommendation system for Spotify-like platforms using the Million Song Dataset. The system suggests the top 10 songs to users by combining global popularity metrics and personalized user behavior, with the goal of maximizing listening time and user satisfaction while addressing challenges like the cold-start problem.

## Dataset

The dataset is sourced from the **Taste Profile Subset** of the **Million Song Dataset**, containing:

### **Song Data**:
- `song_id`: Unique identifier for each song.
- `title`: Title of the song.
- `release`: Album name.
- `artist_name`: Artist name.
- `year`: Release year.

### **User Interaction Data**:
- `user_id`: Unique identifier for each user.
- `song_id`: Unique identifier for each song.
- `play_count`: Number of times the user played the song.

### Dataset Statistics:
- **20 million interactions**.
- **3,155 unique users**.
- **563 unique songs**.
- **232 unique artists**.

## Objectives

- Recommend the top 10 songs a user is most likely to enjoy.
- Solve the cold-start problem for new users.
- Personalize song recommendations using collaborative filtering.
- Analyze listening behaviors to identify top songs and influential users.
- Provide scalable solutions for music streaming platforms.

## Methods

### Data Preprocessing:
- Removed songs with **≤5 play counts** to reduce noise from low-engagement tracks.
- Label encoded user and song IDs for matrix compatibility.
- Explored dataset trends (e.g., peak song releases in **2007**).

### Model Development:

#### 1. **Rank-Based Recommendation System**:
- Recommended globally popular songs based on **average play counts**.
- Applied a **minimum interaction threshold** (e.g., 100 plays) to ensure recommendations reflect meaningful popularity.
- Designed to handle **cold-start users** without historical data.

#### 2. **User-User Collaborative Filtering**:
- Implemented using **K-Nearest Neighbors (KNN)** with **Pearson correlation** to find users with similar listening patterns.
- Recommended songs highly rated by similar users.
- Designed to improve personalization as user listening history grows.

### Evaluation:
- No explicit numerical evaluation metrics (e.g., RMSE, Precision@K) computed.
- Assessed success through top-10 song rankings and user similarity analyses.
- Focused on balancing popular song recommendations with personalized discovery.

## Results

- Popularity-based recommendations ensured immediate engagement for new users.
- Collaborative filtering provided personalized recommendations once sufficient user data was available.
- Identified key insights:
  - ~90% of songs had very low play counts (≤5).
  - The song **“Use Somebody”** was the most played in the dataset.
  - User ID **61472** had the highest overall interaction.
  - Song releases peaked in **2007** within the dataset.

## Business/Scientific Impact

- Enabled dynamic, scalable music recommendation pipelines for streaming services.
- Addressed the **cold-start problem** using rank-based recommendations while offering personalization through collaborative filtering.
- Recommended:
  - Utilizing rank-based methods for new users.
  - Transitioning to collaborative filtering for users with sufficient listening history.
  - Filtering out low-frequency songs to focus on meaningful engagement.
  - Regular model retraining as new songs, users, and play counts are added.
- Enhanced user retention by minimizing irrelevant recommendations and maximizing discovery of relevant songs.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Surprise Library (for KNN-based collaborative filtering)
- Matplotlib
- Seaborn

## How to Run

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/million-song-recommendation-system.git
    ```

2. Install required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Launch Jupyter Notebook:
    ```bash
    jupyter notebook
    ```

4. Open and run the notebook to:
   - Preprocess datasets.
   - Train rank-based and collaborative filtering models.
   - Generate top-10 song recommendations.
   - Analyze listening trends and dataset insights.

## Future Work

- Integrate **Item-Item Collaborative Filtering** to compare performance with User-User models.
- Incorporate **Matrix Factorization** (e.g., SVD) for latent feature extraction and deeper personalization.
- Develop **hybrid recommender systems** that combine content-based and collaborative filtering.
- Deploy as an interactive API or web application for real-time recommendations.
- Expand feature engineering to include genres, moods, and user context (time of day, location, etc.).
