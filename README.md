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

### 🔹 Model 1: Predicting Number of Movies per Year

**Objective:** Predict the total number of movies produced each year.  
- **Input Feature:** Year  
- **Output:** Number of movies released  

**Model:** `LinearRegression()` from `sklearn.linear_model`

**Example Prediction Result:**
- Predicted movies in 2020: **~327**
- Actual movies released (Google data): **329**

**Model Remarks:**
The model showed excellent predictive accuracy, by predicting total movies produced in the future with **99%** accuracy.

### 🔹 Model 2: Predicting Movie Popularity Score Based on Budget

**Objective:** Predict movie **popularity score** using its **budget**.  
- **Train/Test Split:** 70% / 30%
- **Input:** Budget  
- **Output:** Popularity

**Model:** `LinearRegression()` from `sklearn.linear_model`

**Example Prediction Result:**
> For a movie with a $280 million budget, predicted popularity score ≈ **6.0**

**Model Remarks:**
This model helps estimate how budget influences potential popularity of a movie.

## Movie Recommendation Systems

This project features **two** different movie recommendation techniques: one that finds movies with _similar_ content using _keywords_, and another that matches movie titles based on _text similarity_.

### 1️⃣ Keyword-Based Recommendation System

**Goal:** Recommend similar movies based on shared keywords (themes, genres, plots).

**Technique:**
- Extract keywords for each movie.
- Split keyword strings into multiple fields.
- Compare selected movie keywords with others.
- Recommend top 5 matching titles.

**Example:**
> Input Movie: **Terminator Genisys**  
> **Top 5 Recommendations:**
> - Interstellar  
> - Terminator Salvation  
> - Megamind  
> - Justice League: Crisis on Two Earths  
> - The Matrix

**Recommendation Algorithm Remarks:**

This recommendation provides remarkable content-based movies recommendation using keyword matching.

---

### 2️⃣ Fuzzy Matching Movie Recommender

**Goal:** Suggest movies with titles similar to the user’s input (string similarity).

**Technique:**
- Uses `fuzzywuzzy` library for partial ratio string matching.
- Recommends movies whose titles share ≥**90%** similarity.

**Example Input:**
> `"Furious"`

> **Output Suggestions:**
> - Furious 7  
> - Fast & Furious  
> - The Fast and the Furious  
> - Fast & Furious 6  
> - 2 Fast 2 Furious  

**Recommendation Algorithm Remarks:**

This recommendation technique allows flexible movie title matching even with typos or partial inputs.

---

## Conclusions

- The first research question **"What were the Top 5 Genres throughout the years?"** has shown useful results, as the most popular genre turned out to be **Drama**. Perhaps it is because Adventure and Science Fiction movies are more expensive to produce so they are more rarely made than **Drama, Comedy, Thriller**. Believe it or not, this data could be extremey useful for the 'Production Companies', because now they know which type of movies tend to be more popular among the masses and this could help them to drive more potential customers and eventually more sales. 

- The second research question **"How did the amount of movies produced changed over time?"** gave a well defined increasing trend for movies released. The graph also shows that a peak was attained in the year 2011 for the most movies released. Also, according to Wikipedia, **Film critic Scout Tafoya considers 2011 as the best year for cinema.** 

- The third research question **"What is the Average Running Time Of All the Movies?"** shows an accurate result of approximately 106 minutes. This is also evident from the histogram which is plotted against Running Time and Number Of Movies.

- The fourth research question **"How does the budget changes throughout the years?"** shows quite useful results to the users because users can observe that throughout the years the budget has been increasing throughout the years and suddenly skyrockets in the year 2011, which is considered as the best year for cinema according to Wikipedia. In 2011, **Pirates of the Caribbean: On Stranger Tides** is the maximum budget movie till this day, with a maximum budget of 380 Million Dollars USD.

- The fifth research question **"What should be an appropriate budget for a movie to succeed?"** has shown surprising results. Some useful deductions which are clearly evident from the graph are it's not necessary for a movie to become popular and succeed even if it has a higher budget and vice versa.

## Authors

* **Sualeh Alam** - [SualehAlam](https://github.com/sualehalam) 

## License 

![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)
