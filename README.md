# IMDB Analysis and Movies Recommendation System

<img width="1400" height="700" alt="image" src="https://github.com/user-attachments/assets/298ab2fe-f71b-49bb-a092-a47ddcbf3588" />

## Introduction
A data science and machine learning project exploring the **IMDB (Internet Movie Database)** dataset to analyze movie trends, build predictive models, create a content-based movie recommendation system. and visualize film keywords through word clouds.


### Dataset Schema:

The movie dataset, which is originally from **[Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata),** was cleaned and provided by Udacity. This data set contains information about 5,000 movies collected from The Movie Database (TMDb) and the whole dataset duration covers from 1960 to 2015. Contains data such as `title, cast, director, runtime, budget, revenue, release year` etc. 
- Certain columns, like `‘cast’` and `‘genres’`, contain multiple values separated by pipe (|) characters.
- There are some odd characters in the `‘cast’` column. Nothing to care much of, I leave them as is.
- The final two columns ending with `“_adj"` show the budget and revenue of the associated movie in terms of 2010 dollars, accounting for inflation over time.

## Research Questions for Analysis
 1. What were the Top 5 Genres throughout the years?
 2. How did the amount of movies produced changed over time?
 3. What is the Average Running Time Of All the Movies?
 4. How does the budget changes throughout the years?
 5. What should be an appropriate budget for a movie to succeed?


## 📈 Linear Regression Models

### 🔹 Model 1 — Predicting Number of Movies per Year

**Objective:** Predict the total number of movies produced each year.  
- **Input Feature:** Year  
- **Output:** Number of movies released  

**Model:** `LinearRegression()` from `sklearn.linear_model`

**Result:**
- Predicted movies in 2020: **~327**
- Actual movies released (Google data): **329**
- **Coefficient:** 7.41 → Indicates steady yearly growth in production.

✅ *The model achieved excellent predictive accuracy on historical data.*

---

### 🔹 Model 2 — Predicting Movie Popularity Based on Budget

**Objective:** Predict movie **popularity score** using its **budget**.  
- **Train/Test Split:** 70% / 30%
- **Input:** Budget  
- **Target:** Popularity

**Model Evaluation:**
- **Intercept:** 0.667  
- **Coefficient:** 1.89 × 10⁻⁸  
- **RMSE:** 1.698 → Indicates low error and high accuracy.

**Example Prediction:**
> For a movie with a $280 million budget, predicted popularity score ≈ **6.0**

✅ *Helps estimate how budget influences potential popularity.*


## Authors

* **Sualeh Alam** - [SualehAlam](https://github.com/sualehalam) 

## License 

![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)
